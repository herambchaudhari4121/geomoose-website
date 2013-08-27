GeoMOOSE
********

Welcome to GeoMOOSE
===================

Welcome to the GeoMOOSE website.  For first time users, we hope this site is easy to use and understand.  For returning users, we hope this is a pleasant new experience.  This new format for the website has been chosen for its ease of maintenance, ease of portability, and compact delivery size.

What is GeoMOOSE?
-----------------
GeoMOOSE is a Web Client JavaScript Framework for displaying distributed cartographic data.  GeoMOOSE has a number of strengths including modularity, configurability, and delivers a number of core functionalities in its packages.  GeoMOOSE is also very light weight for servers making it easy to handle a large number of users, with a large number of layers, and a large number of services without stressing a server.

The GeoMOOSE core is written using JavaScript and HTML.  It is entirely possible to run GeoMOOSE with nothing more than a basic web server (Nginx, Apache, IIS).  But besides the basic client core, GeoMOOSE also comes prepackaged with a number of built in services written in PHP.  These services add the ability to perform drill-down identify operations, selection operations, and search data sets.  If you have existing scripts that perform similar functions, GeoMOOSE can be tuned to work with those services, no matter which language they were written.

Being an open source project GeoMOOSE is also built upon other open source projects:
	* `MapServer <http://www.mapserver.org>`_
	* `OpenLayers <http://www.openlayers.org>`_
	* `Dojo Toolkit <http://dojotoolkit.org>`_


Why GeoMOOSE?
-------------

.. only:: html

	.. include:: info/why_abstract.rst

	:doc:`Read More <info/why>`

.. only:: not html

	.. include:: info/why_text.rst


GeoMOOSE Gallery
----------------

See working examples of real-world GeoMOOSE implementations. By viewing `the GeoMOOSE Gallery <http://www.geomoose.org/wiki/index.php/GeoMOOSE_Gallery>`_.

GeoMOOSE Documentation
======================
.. toctree::
	:maxdepth: 1

	developer/index
	info/license	

GeoMOOSE Support
================

.. toctree::
	:maxdepth: 1

	info/mailing_lists
	info/commercial_support

.. include:: news.rst

