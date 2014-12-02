.. _how_to_release:


GeoMOOSE Release Procedure
==========================
Follow :ref:`rfc3` and this file

* If not already created, create /releases/M.m.r.txt, summarizing changes from the previous release.  It may help to look at the GitHub issues related to the release milestone and the git commit messages leading up to the release.

* That file should include new features, changed features, and depreciated features.  Changes to the mapbook should be specifically noted along with other items that will cause breaking changes during upgrades.  A MapServer and MS4W version (and implicitly PHP, etc) recommendation should be included too.

* Update `VERSIONS.rst` to explicitly define the versions of PHP and MapServer used during development.  Recommendations on Apache and MS4W versions should also be present.

* Read the documentation and remove outdated parts.

* Update FAQ (remove no longer relevant questions, add new questions).

* Ensure that release exactly matches something in Git.  Tag and branch (then push) appropriately.

* Update documentation as needed keeping in mind that the versioned documentation on the website pulls from different Git branches of geomoose-docs.

* Publish the release:

  * Generate the distribution files (see below).

  * Update geomoose-website/source/downloads.rst with new links

  * Update the news in index.rst (link to /releases/M.m.r.txt), move some of the existing stuff to previous :doc:`../info/old_news` if needed

  * Put the word out on geomoose-users email list and other locations (news_item@osgeo.org, SlashGeo?, etc)

Creating an Official Release
----------------------------

Example procedure::

	#
	# Make a local clean repo
	#
	
	git clone --recursive git@github.com:geomoose/geomoose.git
	cd geomoose
	
	#
	# Merge with the correct release branch
	#
	
	# Update Docs
	cd docs
	git pull
	git checkout -b r2.7 origin/r2.7
	git merge master
	# conflict in source/conf.py
	# Fix release conflict on line in source/conf.py
	#  change to 2.7.1
	git add source/conf.py
	git commit
	git tag r2.7.1
	git remote set-url --push origin git@github.com:geomoose/geomoose-docs.git
	git push
	git push --tags
	cd ..
	
	# Update JS
	cd js
	git pull
	git checkout -b r2.7 origin/r2.7
	git merge master
	# Update version in geomoose.html and geomoose_dev.html
	# HTML->Title, Footer
	git add geomoose.html geomoose_dev.html
	git commit -m 'Bump version number to 2.7.1"
	git tag r2.7.1
	git remote set-url --push origin git@github.com:geomoose/geomoose-js.git
	git push
	git push --tags
	cd ..
	
	# Update Services
	cd services
	git pull
	git checkout -b r2.7 origin/r2.7
	git merge master
	git tag r2.7.1
	git remote set-url --push origin git@github.com:geomoose/geomoose-services.git
	git push
	git push --tags
	cd ..
	
	#
	# Update Demo
	#
	
	git pull
	git checkout -b r2.7 origin/r2.7
	git merge master
	git add docs js services
	git commit -m 'Update for 2.7.1'
	git tag r2.7.1
	git push
	git push --tags
	
	
	###
	### Update Build Bot (on geomoose.org)
	###
	
	### Update Demo and "Binary builds/downloads"
	
	# if this is a new branch
	 BRANCH=2.7
	 cd /srv/demo/html
	 ln -s ../src/$BRANCH $BRANCH
	
	 cd /srv/demo/src
	 git clone --recursive https://github.com/geomoose/geomoose.git $BRANCH
	 cd $BRANCH
	 git checkout r$BRANCH
	 git submodule update --recursive --init

	 # cd /srv/demo
	 # copy build*-2.7.sh to build*-$BRANCH.sh
	 # edit build*-$BRANCH.sh to point to new version
	 # edit /etc/apache2/sites-enabled RewriteRules for new branch
	# end if this is a new branch
	
	cd /srv/demo
	# Update version in zip filename at end of build_ms4w-2.7.sh 
	# Update version at beginning of build_tgz-2.7.sh

	# Update the Demo, and build new release packages
	./update-2.7.sh
	# Check downloads for correctness
	
	
	### Update Docs
	# Nothing to do for existing branch.
	# For a new branch
	BRANCH=2.7
	cd /srv/docs/src
	git clone https://github.com/geomoose/geomoose-docs.git $BRANCH
	cd $BRANCH
	git checkout r$BRANCH
	
	cd /srv/docs/src/ntdocs
	git clone https://github.com/geomoose/geomoose-js.git $BRANCH
	cd $BRANCH
	git checkout r$BRANCH
	
	# Update /srv/docs/update.sh to build the branch.
	# - Only auto build master and supported stable branch
	#   as others shouldn't change
	# Update /etc/apache2/sites-enabled/docs to default to new branch RewriteRule
	
	###
	### Back on local machine
	###
	
	# Update Website NEWS and Downloads
	git clone git@github.com:geomoose/geomoose-website.git
	cd geomoose-website/source
	# Add announcement to news.rst
	# Add release notes in releases/$VERSION.rst based on tickets closed
	# Update downloads.rst
	git push

Example support scripts as used on the server

update-2.7.sh::

	#!/bin/bash
	
	cd /srv/demo/src/2.7
	
	# Update to latest verion
	(cd js && git checkout -- geomoose.html)
	git pull --recurse-submodules=yes
	git submodule update --recursive --init
	
	# Make sure link for PHP is in place
	cd js
	ln -s ../services/php .
	
	# Build JavaScript
	cd libs
	./build_js.sh
	
	# Update title to include ref (master only)
	#cd ../..
	#HEAD=g$(git rev-parse --short HEAD)
	#sed -i -e "s/\(<title>\)\(.*\)\(<\/title>\)/\1\2 ($HEAD)\3/" js/geomoose.html
	
	# Make distribution packages
	/srv/demo/build_ms4w-2.7.sh
	/srv/demo/build_tgz-2.7.sh
	

build_tgz-2.7.sh::

	#!/bin/bash
	
	cd /srv/demo/src/2.7
	
	PKG_DIR="tgz_pkg_build"
	VERSION="2.7.1"
	
	# Make temp working directory for packaging.
	mkdir -p "${PKG_DIR}"
	
	# Copy GeoMoose components into the apps directory.
	APP_DIR="${PKG_DIR}/geomoose-${VERSION}"
	mkdir -p "${APP_DIR}"
	
	cp -vr conf         ${APP_DIR}/conf
	cp -vr docs         ${APP_DIR}/sphinx-docs
	cp -vr maps         ${APP_DIR}/maps
	cp -vr js           ${APP_DIR}/htdocs
	
	rm ${APP_DIR}/htdocs/php # Replace php symlink with real thing
	cp -vr services/php ${APP_DIR}/htdocs/php
	
	cp -v README.md ${APP_DIR}/README.txt
	cp -v LICENSE ${APP_DIR}/LICENSE.txt
	
	# Setup the default configuration
	cp -v ${APP_DIR}/conf/unix_local_settings.ini ${MS4W_APP_DIR}/conf/local_settings.ini
	
	# Compress JS libraries (only needed for dev)
	( cd ${APP_DIR}/htdocs/libs && \
	  tar czvf OpenLayers.tgz OpenLayers && rm -rf OpenLayers && \
	  tar czvf dojo.tgz dojo && rm -rf dojo && \
	  tar czvf proj4js.tgz proj4js && rm -rf proj4js \
	)
	
	git rev-parse --short HEAD > ${APP_DIR}/RELEASE_VERSION.txt
	
	# Cleanup Extra Files
	find ${PKG_DIR} -name '.git' -exec rm '{}' ';'
	find ${PKG_DIR} -name '*.in' -exec rm '{}' ';'
	
	# Create the TGZ file
	( cd "${PKG_DIR}" && \
	  tar czvf geomoose-${VERSION}.tar.gz geomoose-${VERSION} && \
	  mv geomoose-${VERSION}.tar.gz /srv/www/downloads/geomoose-${VERSION}.tar.gz
	)
	
	# Cleanup after ourselves
	rm -rf "${PKG_DIR}"
	

build_ms4w-2.7.sh::

	#!/bin/bash
	
	cd /srv/demo/src/2.7
	
	PKG_DIR="ms4w_pkg_build"
	
	# Make temp working directory for packaging.
	mkdir -p "${PKG_DIR}"
	
	# Build the Base MS4W directory structure.
	rm -rf "${PKG_DIR}"/ms4w
	cp -vr ms4w "${PKG_DIR}"
	
	# Copy GeoMoose components into the apps directory.
	MS4W_APP_DIR="${PKG_DIR}/ms4w/apps/geomoose2"
	mkdir -p "${MS4W_APP_DIR}"
	
	cp -vr conf         ${MS4W_APP_DIR}/conf
	cp -vr docs         ${MS4W_APP_DIR}/sphinx-docs
	cp -vr maps         ${MS4W_APP_DIR}/maps
	cp -vr js           ${MS4W_APP_DIR}/htdocs
	
	rm ${MS4W_APP_DIR}/htdocs/php # Replace php symlink with real thing
	cp -vr services/php ${MS4W_APP_DIR}/htdocs/php
	
	cp -v README.md ${MS4W_APP_DIR}/README.txt
	cp -v LICENSE ${MS4W_APP_DIR}/LICENSE.txt
	
	# Setup the default configuration
	cp -v ${MS4W_APP_DIR}/conf/ms4w_local_settings.ini ${MS4W_APP_DIR}/conf/local_settings.ini
	
	# Compress JS libraries (only needed for dev)
	( cd ${MS4W_APP_DIR}/htdocs/libs && \
	  zip OpenLayers.zip -r OpenLayers && rm -rf OpenLayers && \
	  zip dojo.zip -r dojo && rm -rf dojo && \
	  zip proj4js.zip -r proj4js && rm -rf proj4js \
	)
	
	git rev-parse --short HEAD > ${MS4W_APP_DIR}/RELEASE_VERSION.txt
	
	# Cleanup Extra Files
	find ${PKG_DIR} -name '.git' -exec rm '{}' ';'
	find ${PKG_DIR} -name '*.in' -exec rm '{}' ';'
	
	# Create the ZIP file
	( cd "${PKG_DIR}" && \
	  zip GeoMOOSE-2.7-MS4W.zip -r ms4w && \
	  mv GeoMOOSE-2.7-MS4W.zip /srv/www/downloads/GeoMOOSE-2.7.1-MS4W.zip
	)
	
	# Cleanup after ourselves
	rm -rf "${PKG_DIR}"
