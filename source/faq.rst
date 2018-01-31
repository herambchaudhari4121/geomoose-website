GeoMoose FAQ
============

Why GeoMoose?
-------------

.. only:: html

	.. include:: info/why_abstract.rst

	:doc:`Read More <info/why>`

.. only:: not html

	.. include:: info/why_text.rst

.. Silence not in toctree warnings for toolbar/main page linked pages
.. toctree::
  :hidden:

  info/why


How long has GeoMoose existed?
------------------------------

The first versions of GeoMoose were released in 2005 and it has been under constant development since that time.

Is GeoMoose Open Source? How Open?
----------------------------------

GeoMoose *is* Open Source! It is both *free* as in beer and *free* as in freedom. In fact, GeoMoose is an `OSGeo Project <https://www.osgeo.org/projects/geomoose/>`_ which means that GeoMoose has been vetted for openness and sustainability. GeoMoose is released under a MIT-style license: :doc:`info/license`.  Development happens in the open on our `GitHub <https://github.com/geomoose>`_ page and on our :doc:`info/mailing_lists`.


What do I need to run GeoMoose?
-------------------------------

To serve GeoMoose to users you need a web server capable of handling your desired number of users.  As GeoMoose itself is really a collection of static pages the real key is ensuring that the mapping server software is capable of handling the number of mapping requests users will generate.  The GeoMoose development team is a huge fan of MapServer and we even provide packages for MS4W that let's Windows centric environments get-up-and-go within minutes!

As a user, GeoMoose requires modern browsers.  That means relatively new versions of Firefox and we only test on IE11 and Edge.  Older IE versions will not be supported.


What is the GeoMoose 'stack'?
-----------------------------

GeoMoose uses a number of underlying technologies. All of which are evolving. This is a *very* brief summary of what GeoMoose has used over the years:

* GeoMoose 3.X: React, Redux, OpenLayers 4
* GeoMoose 2.X: Dojo Toolkit, OpenLayers 2
	* GeoMoose 2.X also used Mapserver's PHP MapScript to provide some demonstration services.
* GeoMoose 1.X: Used a completely home-built Mapping and UI library.

