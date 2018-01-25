.. _rfc3:

RFC 3: GeoMoose Release Process
====================================================================

:Author: Eli Adam,  (inspiration also from `MapServer RFC 34 <http://mapserver.org/development/rfc/ms-rfc-34.html>`_)
:Contact: eadam at ...
:Status: Adopted
:Last Updated: 06/25/2013


Summary
-----------

This document describes the GeoMoose Release Process.  The purpose of the Release Process is to ensure that GeoMoose releases continue at a high quality level.  This is best accomplished through following a documented repeatable process.  A Release Manager will be responsible for coordinating or implementing these details.  


Details
-----------------------

* GeoMoose releases will be made based on this RFC and :ref:`how_to_release`.
* GeoMoose releases start with a discussion and motion on the email list.  This should cover an outline of the schedule, a feature list or freeze date, and nomination of a Release Manager.
* The Release Manager is given wide latitude to make decisions pertaining to the Release Process.
* The Release Manager can delegate parts of the process to others but must make sure that the work gets done.  
* The Release Manager should keep all informed of progress during the Release Process.
* GeoMoose releases should be well tested, well documented, and well publicized according to procedures in :ref:`how_to_release`.

Versioning of Releases
-----------------------

GeoMoose version numbers (starting with 2.6.0) follow Semantic Versioning (see http://semver.org for full details).

In short, the version number is broken into three fields: a major version, a minor version and a patch version.  For example the version 2.0.1 represents major version 2, minor version 0, and patch version 1. The major version is incremented when backwards incompatible changes to the public API.  The minor version is incremented for feature additions that are backwards compatible.  The patch version is updated for bug fixes that are not expected to cause compatibility problems and do not add functionality. A pre-release version (such as a beta or release candidate) will be marked by appending a '-' and a tag indicating the purpose of the pre-release.

The public API of GeoMoose consists of:

	* The GeoMoose JavaScript namespace
	* The Services interface
	* The Configuration files such as the mapbook format


Voting History
---------------
Adopted on 6/25/2013 with PSC +1 votes from Jim, Brian, Brent, Bob, and Eli.

