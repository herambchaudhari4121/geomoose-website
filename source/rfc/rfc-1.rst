RFC 1: Project Steering Committee Guidelines
====================================================================

:Author: Dan Little (inspired by MapServer RFC23 http://mapserver.org/development/rfc/ms-rfc-23.html#rfc23)
:Contact: danlittle at ...
:Status: Adopted
:Last Updated: 09/30/2011


Summary
-----------

This document describes how the GeoMoose Project Steering Committee 
determines membership, and makes decisions on all aspects of the 
GeoMoose project - both technical and non-technical.

Examples of PSC management responsibilities:

* setting the overall development road map
* developing technical standards and policies (e.g. coding standards, 
  file naming conventions, etc...)
* ensuring regular releases (major and maintenance) of GeoMoose software
* reviewing RFC for technical enhancements to the software
* project infrastructure (e.g. CVS/SVN, Bugzilla, hosting options, etc...)
* formalization of affiliation with external entities such as OSGeo
* setting project priorities, especially with respect to project sponsorship
* creation and oversight of specialized sub-committees (e.g. project 
  infrastructure, training) 

In brief the project team votes on proposals on GeoMoose.  Proposals are 
available for review for at least two days, and a single veto is sufficient 
to delay progress though ultimately a majority of members can pass a proposal.

Detailed Process
-----------------------

* Proposals are written up and submitted on the GeoMoose mailing list 
  for discussion and voting, by any interested party, not just 
  committee members.
* Proposals need to be available for review as an RFC posted on the GeoMoose site for at least two business 
  days before a final decision can be made.
* All discussions regarding the RFC should occur on the GeoMoose mailing list.
* Respondents may vote "+1" to indicate support for the proposal and a 
  willingness to support implementation.
* Respondents may vote "-1" to veto a proposal, but must provide clear 
  reasoning and alternate approaches to resolving the problem within 
  the two days.
* A vote of -0 indicates mild disagreement, but has no effect.  A 0 
  indicates no opinion.  A +0 indicate mild support, but has no 
  effect.
* Anyone may comment on proposals on the list, but only members of the 
  Project Steering Committee's votes will be counted.
* A proposal will be accepted if it receives +2 (including the 
  author) and no vetoes (-1).
* If a proposal is vetoed, and it cannot be revised to satisfy all 
  parties, then it can be resubmitted for an override vote in which a 
  majority of all eligible voters indicating +1 is sufficient to pass it.  
  Note that this is a majority of all committee members, not just those who 
  actively vote.
* Upon completion of discussion and voting the author should announce 
  whether they are proceeding (proposal accepted) or are withdrawing 
  their proposal (vetoed).
* The Chair gets a vote.
* The Chair is responsible for keeping track of who is a member of the 
  Project Steering Committee (by updating this document).
* Addition and removal of members from the committee, as well as selection 
  of a Chair should be handled as a proposal to the committee.
* The Chair adjudicates in cases of disputes about voting.
 
When is Vote Required?
-----------------------

* Any change to committee membership (new members, removing inactive members).
* Changes to project infrastructure (e.g. tool, location or substantive 
  configuration).
* Anything that could cause backward compatibility issues.
* Adding substantial amounts of new code.
* Changing inter-subsystem APIs, or objects.
* Issues of procedure.
* When releases should take place.
* Anything dealing with relationships with external entities such as OSGeo.
* Anything that might be controversial.

Observations
----------------

* The Chair is the ultimate adjudicator if things break down.
* The absolute majority rule can be used to override an obstructionist 
  veto, but it is intended that in normal circumstances vetoers need to be 
  convinced to withdraw their veto.  We are trying to reach consensus.
* It is anticipated that separate "committees" will exist to manage 
  conferences, documentation and web sites.  That said, it is expected 
  that the PSC will be the entity largely responsible for creating any 
  such committees.

Committee Membership
---------------------

The PSC is made up of individuals consisting of technical contributors 
(e.g. developers) and prominent members of the GeoMoose user community.  
There is no set number of members for the PSC although the initial desire 
is to set the membership at six.

Adding Members
..............

Any member of the GeoMoose mailing list may nominate someone for 
committee membership at any time. Only existing PSC committee members may 
vote on new members.  Nominees must receive a majority vote from existing 
members to be added to the PSC.

Stepping Down
.............

If for any reason a PSC member is not able to fully participate then they 
certainly are free to step down.  If a member is not active (e.g. no 
voting, no IRC or email participation) for a period of two months then 
the committee reserves the right to seek nominations to fill that position.
Should that person become active again (hey, it happens) then they would 
certainly be welcome, but would require a nomination.

Membership Responsibilities
-----------------------------

Guiding Development
...............................

Members should take an active role guiding the development of new features 
they feel passionate about. Once a change request has been accepted 
and given a green light to proceed does not mean the members are free of 
their obligation. PSC members voting "+1" for a change request are 
expected to stay engaged and ensure the change is implemented and 
documented in a way that is most beneficial to users. Note that this 
applies not only to change requests that affect code, but also those 
that affect the web site, technical infrastructure, policies and standards.

Meeting Attendance
...............................

PSC members are expected to participate in pre-scheduled development 
meetings. If known in advance that a member cannot attend a meeting, 
the member should let the meeting organizer know via e-mail.

Mailing List Participation
...............................

PSC members are expected to be active on the GeoMoose mailing lists, subject to open source mailing list 
etiquette. 

Non-developer members of the PSC are not expected to respond 
to coding level questions on the mailing list, however they 
are expected to provide their thoughts and opinions on user level 
requirements and compatibility issues when RFC discussions take place.

Bootstrapping
-----------------

Initial members are:

* Dan "Ducky" Little
* Jim Klassen
* Bob Basques
* Brian Fischer, Chair
* Eli Adam
* Brent Fraser

Current Members
---------------

* Dan "Ducky" Little, Chair
* Jim Klassen
* Bob Basques
* Brian Fischer 
* Eli Adam
* Brent Fraser
* TC Haddad


Voting History
--------------------

* 09/30/2011 - Adopted by votes from PSC.  +1: Brian, Jim, Dan, Bob, Eli and Brent
* 02/25/2015 - With +1's from Brian, James, Eli, Brent, Duck, Duck becomes Chair, TC Haddad added to PSC.
