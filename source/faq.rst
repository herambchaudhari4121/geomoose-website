GeoMoose FAQ
============

Why GeoMoose?
-------------

.. only:: html

	.. include:: info/why_abstract.rst

	:doc:`Read More <info/why>`

.. only:: not html

	.. include:: info/why_text.rst

How long has GeoMoose existed?
------------------------------

The first versions of GeoMoose were released in 2005 and it has been under constant development since that time.

Is GeoMoose Open Source? How Open?
----------------------------------

GeoMoose *is* Open Source! It is both *free* as in beer and *free* as in freedom. In fact, GeoMoose is an OSGeo Project which means that GeoMoose has been vetted for Open-ness and sustainability.

What do I need to run GeoMoose?
-------------------------------

To serve GeoMoose to users you need a web server capable of handling your desired number of users.  As GeoMoose itself is really a collection of static pages the real key is ensuring that the mapping server software is capable of handling the number of mapping requests users will generate.  The GeoMoose development team is a huge fan of MapServer and we even provide packages for MS4W that let's Windows centric environments get-up-and-go within minutes!

As a user, GeoMoose requires modern browsers.  That means relatively new versions of Firefox and we only test on IE11 and Edge.  Older IE versions will not be supported.

Can I get support for GeoMoose?
-------------------------------

Yes! GeoMoose has a wonderful online community that regularly answers emails on our mailing lists, and any question on our IRC Channel #geomoose on FreeNode.  There are also companies that will support, customize, and even host GeoMoose.  You can learn more about them here:

.. toctree::
	:maxdepth: 1

	info/mailing_lists
	info/commercial_support

I have found a bug. How does it get fixed?
------------------------------------------

First, try sending a message to the mailing list above. This will let the developers know you've found a bug and will help them determine appropriate follow up actions.

Second, we have two issue trackers setup in GitHub depending on the version of GeoMoose being used:

  * `GeoMoose 2 issues <https://github.com/geomoose/geomoose/issues>`_
  * `GeoMoose 3 issues <https://github.com/geomoose/gm3/issues>`_



What is the GeoMoose 'stack'?
-----------------------------

GeoMoose uses a number of underlaying technologies. All of which are evolving. This is a *very* breif summary of what GeoMoose has used over the years:

* GeoMoose 3.X: React, Redux, OpenLayers 4
* GeoMoose 2.X: Dojo Toolkit, OpenLayers 2
	* GeoMoose 2.X also used Mapserver's PHP MapScript to provide some demonstration services.
* GeoMoose 1.X: Used a completely home-built Mapping and UI library.

