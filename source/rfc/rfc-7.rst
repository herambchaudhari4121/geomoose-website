.. _rfc7:

RFC 7: GeoMoose 3.0
====================================================================

:Author: Dan "Ducky" Little
:Contact: @theduckylittle
:Status: Adopted 
:Last Updated: 20 July 2017


Summary
-----------

The web browser and the JavaScript ecology has been evolving all around GeoMoose! 
In keeping with those changes, GeoMoose 3.0 will require a major rewrite to both stay
relevant with the new generation of web technologies and to help extend its reach
and functionality.

Goals
-----

1. Exercise Standards instead of Custom Services.  Previous version of GeoMoose used Perl and PHP in order to provide query services for the user.  3.0 strives to use WMS and WFS standards in order to work with existing service's capabilities.
2. Use a recognizable JavaScript development stack.  This includes using contemporary JavaScript package management and structuring the project in a way that is compatible with the modern JavaScript toolchain. The tentative JavaScript stack is:

  * Webpack + Babel
  * React + Redux
  * OpenLayers 3+

3. Make upgrades easier on users.  Upgrading between even small revisions of GeoMoose has previously been a huge pain point for implementation.  This will be achieved by making a clear distinction between the core GeoMoose library and user/demo application that use the library.  This separation will allow updates to the core library without the sometime complex merges that are sometimes required with the current GeoMoose 2.x series.  As most of the complexity will be contained within the core library, in many cases user applications can be very simple.  The core library will be structured to avoid the need to rework user applications wherever possible.
4. Keep installations simple.  Users should not need to know a specific JavaScript library or require heavy coding in order to create their own GeoMoose deployment.
5. Documentation!
6. Testing - Implement automated testing and coverage.
7. MS4W / Windows compatibility. GeoMoose 3.0.0 and beyond will ensure Windows compatilbity with the development toolchain.


Implementation Tasks
-----------------------

1. Creation of new repositories dedicated to GeoMoose 3 development.

2. Selection of underlying JavaScript libraries for implementation.

3. Code, code, code!

Voting History
---------------

20 July 2017: +1 from Dan "Ducky" Little, Jim Klassen, Brian Fischer, Brent Fraser, TC Hadad, Eli Adam
