GeoMoose News
=============

8/10/2016 - 3.0.0 is OFFICIAL!
------------------------------

With a full year of hard work the GeoMoose team is proud to announce the official 3.0.0 release!

This is the first major rewrite of GeoMoose in nearly 10 years. This newest version offers a great
upgrade over the the 2.X line in GeoMoose:

1. Modern Javascript frameworks. 
   GM3 is based on React, OpenLayers 4, JSTS, Babel, and Webpack. This makes GeoMoose
   development and deployment platform independent and easy to extends.

   Not a fan of React and ES6? No fear! GeoMoose's examples are written in traditional Javascript.

2. We're exercising even more standards.
   GM3 does not use PHP but still can perform identify, select, and buffer operations!
   It does this by using JSTS to do client-side geometry manipulation and the querying capabilities
   of WFS and FeatureServices.

   That also means no more MapServer templates! Templates can now be defined right in the mapbook
   using the Mark.up template engine.

3. There are so many other great features! `Try the Demo <http://demo.geomoose.org>`_ and read the `Quickstarts! <./quickstart.html>`_. The full 3.0.0 documentation can be `found here! <http://geomoose.github.io/gm3/>`_

Finally, a huge **thank you** to the MN.IT with the Minnesota DOT. They provided a lot of technical assistance, review, and funding for this release! 


7/11/2017 - 3.0.0 is Almost Here!
---------------------------------

After a great showing at ITAG, 3.0.0 is getting even closer to release! There's been a few late-changing bugs that will need to be fixed but we expect to have 3.0.0 ready for everyone by the end of the month!

The biggest gulf right now is the documentation. Much of the older documentation and how-tos will still need "ported forward" to make a real release possible.  The code is *really good* but we are missing that solid documentation component to go with it.

If you get any time please check out the demo and file any issues you may find. We want to get the best out of this frist release and it's really starting to gel! We also accept documentation help! If you find a how-to you'd like to rewrite or have solved a problem with 3.0.0 already send it our way. We'd love to put it in!

6/20/2017 - Starting to wrap on 3.0
-----------------------------------

We are getting closer and closer to an official 3.0 release! We've really tackled the last of the major features and can proudly announce that all of the following features work in the latest version of 3.0:

1. Buffering. We're using the ES6-capable version of JSTS to do client-side buffering.  It's been a really great addition and you can see it at work in the new demo.
2. OpenLayers 4. OpenLayers now publishes an `ol` package which is ES6-compatible.  We have adopted it and so now there is no longer a need to separately include OpenLayers in a gm3 application.
3. The metadata tool is back. In all of our development we missed out on the simple metadata tool from the catalog. It's back in the demo.
4. Toolbar drawers. In GM 2.X these were provided by using a very widget heavy set of solutions.  They usually had browser compatibility issues and some struggled to function on touch screens.  The new solution is almost purely CSS based and has been test on modern version of IE, Chrome, Firefox, and on mobile browsers.
5. ArcGIS FeatureServer layers. FeatureServer layers can now be treated the same way as WFS layers. They can be queries and rendered in the browser.  The *AGS Dakota County Rail* layer in the demo has been added as an example to prove how it works and it can be used in the same ways and with services just like any other vector layer.

Thursday, @theduckylittle will be presenting at Iowa's ITAG conference and covering all the new features and doing a live demo.

Please take some time to exercise the demo and file bug reports! The GeoMoose 3 issue list can be found `here on GitHub <https://github.com/geomoose/gm3/issues>`_.

5/2/2017 - Making a (PDF) Mark with GeoMoose 3.0
------------------------------------------------

GeoMoose 3.0 is still moving along! We have put some serious work into preparing packaging and adding a new print tool.  The coolest part? Still no server-side scripts needed to make printing happen! A major design goal is to minimize server-side software in GeoMoose 3.0.  That means no more PHP requirement. There are two major roadblocks to that development:

 1. Buffering.  This still needs to be tackled.  The hope is to use a minified form of JSTS in order to provide client-side buffering of features.
 2. Printing. All of the previous print solutions in GeoMoose used server-side libraries for PHP or Perl.  Now, we are able to use jsPDF and some tricks with OpenLayers to generate a PDF on the client. Major victory!

GeoMoose 3.0 and npm
^^^^^^^^^^^^^^^^^^^^

GeoMoose 3.0 will also be available as a package on `npm <https://www.npmjs.org/>`_! Jim has been hard at work ensure that we have the project structured in such a way that folks can integrate the new GeoMoose into their npm-managed projects. It's not ready quite yet but will be for the first release.

See it all!
^^^^^^^^^^^

Printing is now available in the `Demo <http://demo.geomoose.org/3.0/>`_ and all the code is available on `GitHub <https://github.com/geomoose/gm3>`_.

4/18/2017 - Great things are afoot!
-----------------------------------


3.0 Development
^^^^^^^^^^^^^^^

Development on a fresh new GeoMoose 3.0 is getting really exciting! We've put together a great new architecture while working hard to keep GeoMoose familiar to users and administrators.  Check out the activity on `GitHub <https://github.com/geomoose/gm3>`_ and the new `Demo <http://demo.geomoose.org/3.0/>`_.

GeoMoose will be at FOSS4G 2017 in Boston!
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A new GeoMoose 3.0 workshop will be presented in Boston! If you're coming to Boston, sign up, and learn the new GeoMoose!  The workshop will cover the new concepts, installation, and customization of 3.0.  We are waiting on pins-and-needles in order to hear about our project status presentation.  If that's accepted we'll post here with more information.
 
ITAG 2017
^^^^^^^^^

Acceptance at `ITAG! <https://iowacountiesit.org/itag-conference/>`_ In the Des Moines area in June? Come see @theduckylittle give a run down of GeoMoose 3.0.  It includes a complete summary of the new architecture and development plans for the next year.


4/5/2017 - GeoMoose Security Advisory
-------------------------------------

A security issue in GeoMoose was identified that affects many  versions of GeoMoose.  The earliest version of the bug we have been able to identify is GeoMoose 2.7 but earlier versions of the 2.X series may also be affected. 

The fix for this is easy and works the same for all versions of GeoMoose.  Find your copy of "download.php" and replace it with this one:

- https://github.com/geomoose/geomoose-services/raw/master/php/download.php

This version has been tested and does not exhibit the bug.

*Please* update your GeoMoose installations as soon as possible.

All packages now available have been fixed. 

Thank You,

The GeoMoose Team


.. only:: html
	
	:doc:`info/old_news`

.. only:: not html
	
	.. include:: info/old_news.rst

