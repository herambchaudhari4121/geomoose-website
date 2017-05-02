GeoMOOSE News
=============

5/2/2017 - Making a (PDF) Mark with GeoMOOSE 3.0
------------------------------------------------

GeoMOOSE 3.0 is still moving along! We have put some serious work into preparing packaging and adding a new print tool.  The coolest part? Still no server-side scripts needed to make printing happen! A major design goal is to minimize server-side software in GeoMOOSE 3.0.  That means no more PHP requirement. There are two major roadblocks to that development:

 1. Buffering.  This still needs to be tackled.  The hope is to use a minified form of JSTS in order to provide client-side buffering of features.
 2. Printing. All of the previous print solutions in GeoMOOSE used server-side libraries for PHP or Perl.  Now, we are able to use jsPDF and some tricks with OpenLayers to generate a PDF on the client. Major victory!

GeoMOOSE 3.0 and npm
^^^^^^^^^^^^^^^^^^^^

GeoMOOSE 3.0 will also be available as a package on `npm <https://www.npmjs.org/>`_! Jim has been hard at work ensure that we have the project structured in such a way that folks can integrate the new GeoMOOSE into their npm-managed projects. It's not ready quite yet but will be for the first release.

See it all!
^^^^^^^^^^^

Printing is now available in the `Demo <http://demo.geomoose.org/3.0/demo/>`_ and all the code is available on `GitHub <https://github.com/geomoose/gm3>`_.

4/18/2017 - Great things are afoot!
-----------------------------------


3.0 Development
^^^^^^^^^^^^^^^

Development on a fresh new GeoMOOSE 3.0 is getting really exciting! We've put together a great new architecture while working hard to keep GeoMOOSE familiar to users and administrators.  Check out the activity on `GitHub <https://github.com/geomoose/gm3>`_ and the new `Demo <http://demo.geomoose.org/3.0/demo/>`_.

GeoMOOSE will be at FOSS4G 2017 in Boston!
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A new GeoMOOSE 3.0 workshop will be presented in Boston! If you're coming to Boston, sign up, and learn the new GeoMOOSE!  The workshop will cover the new concepts, installation, and customization of 3.0.  We are waiting on pins-and-needles in order to hear about our project status presentation.  If that's accepted we'll post here with more information.
 
ITAG 2017
^^^^^^^^^

Acceptance at `ITAG! <https://iowacountiesit.org/itag-conference/>`_ In the Des Moines area in June? Come see @theduckylittle give a run down of GeoMOOSE 3.0.  It includes a complete summary of the new architecture and development plans for the next year.


4/5/2017 - GeoMOOSE Security Advisory
-------------------------------------

A security issue in GeoMoose was identified that affects many  versions of GeoMoose.  The earliest version of the bug we have been able to identify is GeoMoose 2.7 but earlier versions of the 2.X series may also be affected. 

The fix for this is easy and works the same for all versions of GeoMoose.  Find your copy of "download.php" and replace it with this one:

- https://github.com/geomoose/geomoose-services/raw/master/php/download.php

This version has been tested and does not exhibit the bug.

*Please* update your GeoMoose installations as soon as possible.

All packages now available have been fixed. 

Thank You,

The GeoMOOSE Team

1/12/2017 - GeoMOOSE Version 2.9.2 Released
-------------------------------------------

GeoMOOSE 2.9.2 is a bug fix release that includes fixes for 2.9.1 and 2.9.2. (2.9.1 was never officially released).

See :ref:`2.9.1_Release` and :ref:`2.9.2_Release` for details.

5/19/2016 - GeoMOOSE Version 2.9.0 Released
-------------------------------------------

After months of hard work, we are pleased to bring you GeoMOOSE 2.9.0.

There were lots of new stuff and bug fixes for 2.9.0.

See :ref:`2.9.0_Release` for details.

10/2/2015 - GeoMOOSE Version 2.8.1 Released
-------------------------------------------

The GeoMOOSE project is excited to announce the 2.8.1 release!

The 2.8.1 release fixes bugs that were in 2.8.0.

Check the :ref:`2.8.1_Release` for more details.


6/20/2015 - GeoMOOSE Version 2.8.0 Released
-------------------------------------------

The GeoMOOSE project is excited to announce the 2.8.0 release!

2.8.0 fixes bugs that were in 2.7.1 and also includes some new exciting features.

Check the :ref:`2.8.0_Release` for more details.



.. only:: html
	
	:doc:`info/old_news`

.. only:: not html
	
	.. include:: info/old_news.rst

