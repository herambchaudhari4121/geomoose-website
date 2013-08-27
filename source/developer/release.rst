.. _how_to_release:


GeoMOOSE Release Procedure
==========================
Follow :ref:`rfc3` and this file

* If not already created, create /releases/M.m.r.txt, summarizing changes from the previous release, review the `revision log <http://trac.osgeo.org/geomoose/log/>`_.

* That file should include new features, changed features, and depreciated features.  Changes to the mapbook should be specifically noted along with other items that will cause breaking changes during upgrades.  A MapServer and MS4W version (and implicitly PHP, etc) recommendation should be included too.

* Update `VERSIONS.rst` to explicitly define the versions of PHP and MapServer used during development.  Recommendations on Apache and MS4W versions should also be present.

* Read the documentation and remove outdated parts.

* Update FAQ (remove no longer relevant questions, add new questions).

* Create beta and release candidate .zip and .tar.gz (transfer to webmasters -- Jim/Dan )

* Release betas and get feedback until there is no feedback about directly relevant items.

* Cut a release candidate once you think that everything is in order.  Announce the release candidate for review for at least 2 weeks.  In this period of time, it is also appropriate for you to deploy in production since you are asserting that it is stable and (significant) bug free.  Publish a specific revision with this.  

* If significant bugs are reported, fix and cut a new release candidate.  If no major bugs, then announce that the release candidate has officially been promoted to the official release (if you want, you can do this with a motion and support of the PSC).

* Ensure that release exactly matches something in SVN.  Tag and branch appropriately.

* Update documentation as needed keeping in mind that the versioned documentation on the website pulls from different SVN branches.

* Update downloads.rst with new links

* Update the news in index.rst (link to /releases/M.m.r.txt), move some of the existing stuff to previous :doc:`../info/old_news` if needed

* Open an OSGeo SAC Trac ticket to update downloads (unless we just have a redirect there to our website)

* Put the word out on email list and other locations (news_item@osgeo.org, SlashGeo?, etc)

Creating an Official Release
----------------------------

Official releases differ from Betas.  Beta testers are advised to download nightly builds and test against them.  Release versions lead to an update in documentation and standard tarballs.  This is to help future administrators repeatably create releases.

* Double check that geomoose.html and geomoose_dev.html match the current version. (Title and footer).

* Double check that the latest build file matches the current revisions number. ::
 
	cd htdocs/libs/dojo*/util/buildscripts
	./build_geomoose2.sh

* Create a commit point for the code. ::

	# cd to the trunk directory.
	svn commit -m 'Updated build to ensure completeness before 2.X.Y release.'

* If this is a new major release create a branch and a tag. (e.g. 2.6, 2.8) ::

	cd geomoose2/
	svn cp trunk branches/geomoose-2.6
	svn cp trunk tags/geomoose-2.6.0 

* If this is a major or minor relase, create a tag. ::

	svn cp branches/geomoose-2.6 tags/geomoose-2.6.1

* Commit the tags or branches with the version numbers. ::

	svn commit -m 'Created branch/tags for the 2.X.Y release'

* Login to the webserver and ... ::

	# get the latest changes from svn
	cd /srv/svn
	svn up

	# tag a version
	cd /srv/geomoose
	# update the nightly builds to the latest revision, from which we'll make a 
	# version.  This doesn't work for branched versions.
	./update_nightly_builds.sh

	# now take the nightly and call it a version number
	./tag_nightly.sh 2.6.0

	# Now let's build the docs.
	cd /srv/svn/geomoose2/tags/geomoose-2.6.0/sphinx-docs
	make html

	# And now for the API.
	cd /srv/svn/geomoose2/tags/geomoose-2.6.0/
	mkdir apidocs
	/srv/geomoose/naturaldocs/naturaldocs -i htdocs/geomoose -o html ./apidocs -p ./ntdocs

* Phew, that was fun. Next we need to add a line to ``/srv/geomoose/httpd.confd/geomoose_2.6.0.conf`` :: 

	Alias /2.6.0/api /srv/svn/geomoose2/tags/geomoose-2.6.0/apidocs/
	Alias /2.6.0 /srv/svn/geomoose2/tags/geomoose-2.6.0/sphinx-docs/build/html/ 
		
	<Location /2.6.0/>
		Allow from all
		Order allow,deny
		Options Indexes FollowSymLinks
	</Location>

* Now we'll point "Current" at the branch so that we can update docs without making an absolute release. ::

	rm /srv/geomoose/current
	ln -s /srv/svn/geomoose2/branches/geomoose-2.6 /srv/geomoose/current

* And restart the web server.  The release should now be happening.




