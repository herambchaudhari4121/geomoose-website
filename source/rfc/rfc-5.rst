.. _rfc5:

RFC 5: Modularize Core GeoMoose Services
====================================================================

:Author: S\. Andrew Sheppard
:Contact: asheppard at ...
:Status: Adopted
:Last Updated: 1/30/2013


Summary
-----------

This document describes a number of changes to the core GeoMoose feature services (particularly ``select.php``, ``query.php``, and ``identify.php``) to make it easier to re-use common output techniques between the services.  The immediate goal is to facilitate re-use of the semi-persistent WMS layers that ``select.php`` creates, making them available for output by ``query.php``.  Once this is done, enabling WFS capabilities for these layers will make it possible to provide standards-based vector interactivity for service results in the GeoMoose client.

The longer-term goal is to modularize the services infrastructure, making it easier both to create new services and to maintain the core GeoMoose service codebase.  Toward this end, this RFC proposes creating base classes that facilitate the generation of various output formats and modes from arbitrary service result sets.

Finally, this RFC proposes documenting the generalized workflow in a language-independent manner, as a first step towards implementing and providing the base classes and/or core services in languages other than PHP.


Implementation Tasks
-----------------------

* Create a ``Service`` base class in PHP with basic functionality for parsing a request and sending XML results to the client.
* Extend this with a ``FeatureService`` subclass, with support for various output routines appropriate for use by services that return feature sets and geometries.
* Implement various output modes for the ``FeatureService`` class, re-using code from existing services to the extent possible.  These modes include:
   * Templated HTML list of results (as in ``identify.php``, etc.)
   * WMS layer (generated in memory, as in ``query.php``)
   * WMS layer (backed by SQLite, as in ``select.php``)
   * WFS layer (by extending existing WMS layer[s])
* Implement client vector interactivity, including display in a Dojo data grid (probably using WFS feature attributes).
* Define mapbook configuration options that can be used by services to set the output mode.
* Refactor the core feature services as subclasses of ``FeatureService``.  Assign appropriate default configurations for the core feature services to provide transparent backwards compatibility.
* Update existing documentation for configuring and creating PHP services.
* Extend documentation with a language-independent description of the service workflow.

Effect on Existing GeoMoose Installations
-----------------------------------------
While the internal refactoring is substantial, it is anticipated that existing GeoMoose users will be able to upgrade without issue, as existing services will default to their current output modes.  In addition, service developers will have the option to utilize the new base classes but will not required to.  In light of RFC 3 and with these considerations in mind, a likely target for integrating these changes into GeoMoose core is version 2.8.0.

Voting History
---------------
Adopted on 1/30/2013 with PSC +1 votes from Bob, Eli, and Brian and +0 from Jim

