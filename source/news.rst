GeoMoose News
=============

8/13/2018 - Performance improvements coming
-------------------------------------------

Finding GeoMoose 3 a little slow? Tests between GeoMoose 2.X and 3
initially showed quite a few performance benefits. We have still
found this to be true but there's always room for improvement! A few 
major components were doing extra memoization and  taking up way
too much memory.

The branch with the performance improvements is still a work in progress
but for this interested the pull request can be found `here <https://github.com/geomoose/gm3/pull/314>`_!

6/25/2018 - GeoMoose 3.2.1 Release
----------------------------------

Add a polyfill to fix an IE11 regression in 3.2.0.

4/12/2018 - GeoMoose 3.2.0 Release
----------------------------------

After fighting quite a few dependency demons in NPM, we've taken
the time to update the build system! All of our dependencies are
now on the the latest versions.  We've also started to add the
npm "lock" file to the repo to prevent inconsistencies with build
and testing.

:ref:`3.2.0_Release` has more details on all the fixed bugs!

11/28/2017 - GeoMoose 3.1.0 Release
-----------------------------------

Many bug fixes! Great set of new features!

See :ref:`3.1.0_Release` for more details!

9/24/2017 - GeoMoose 3.0.1 Release
----------------------------------

Today's GeoMoose 3.0.1 release contains bug fixes and lots of documentation updates.

See :ref:`3.0.1_Release` for details.

9/11/2017 - Still at it! 3.0.1 on the Horizon
---------------------------------------------

After the great feedback from FOSS4G, and some tickets from early adopters, we've been
studiously working towards the 3.0.1 release.  There will be a great collection of small
changes. Stay tuned for a release! 


8/15/2017 - FOSS4G Workshop Day
-------------------------------

@theduckylittle will be teaching a GeoMoose 3.0.0 workshop at FOSS4G in Boston today!

For those who can't make it, we have made the workshop contents available online. 

Find it in the `GitHub pages <https://geomoose.github.io/gm3/workshop/>`_. Fun fact, this Markdown presentation can be turned into
PDF slides using pandoc and beamer!

Look for the GeoMoose 3.0.0 presentation tomorrow!

8/10/2017 - 3.0.0 is OFFICIAL!
------------------------------

With a full year of hard work the GeoMoose team is proud to announce the official 3.0.0 release!

This is the first major rewrite of GeoMoose in nearly 10 years. This newest version offers a great
upgrade over the the 2.X line in GeoMoose:

1. Modern JavaScript frameworks.
   GM3 is based on React, OpenLayers 4, JSTS, Babel, and Webpack. This makes GeoMoose
   development and deployment platform independent and easy to extends.

   Not a fan of React and ES6? No fear! GeoMoose's examples are written in traditional JavaScript.

2. We're exercising even more standards.
   GM3 does not use PHP but still can perform identify, select, and buffer operations!
   It does this by using JSTS to do client-side geometry manipulation and the querying capabilities
   of WFS and FeatureServices.

   That also means no more MapServer templates! Templates can now be defined right in the mapbook
   using the Mark.up template engine.

3. There are so many other great features! `Try the Demo <https://demo.geomoose.org>`_ and read the `Quickstarts! <./quickstart.html>`_. The full 3.0.0 documentation can be `found here! <https://geomoose.github.io/gm3/>`_

Finally, a huge **thank you** to the MN.IT with the Minnesota DOT. They provided a lot of technical assistance, review, and funding for this release! 


:doc:`info/old_news`

.. Silence not in toctree warnings for toolbar/main page linked pages
.. toctree::
  :hidden:

  info/old_news
