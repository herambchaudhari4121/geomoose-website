.. _rfc4:

RFC 4: GeoMoose Commit Management
====================================================================

:Date: 2013-05-28
:Author:  Bob Basques,  Jim Klassen ( Heavy inspiration, and borrowing from `MapServer RFC 7.2 <http://mapserver.org/development/rfc/ms-rfc-7.2.html>`_)
:Contact: bob DOT basques at ci DOT stpaul DOT mn DOT us
:Contact: klassen DOT js at gmail DOT com
:Status: Adopted
:Last Updated: 2013-07-25


Purpose
-------

To formalize Git push access, and specify guidelines for Git 
committers.  More information on working with Git in GeoMoose can be
found at https://github.com/mapserver/mapserver/wiki/WorkingWithGit.


Election to Git Push Access
---------------------------

Permission for Git push access shall be provided to new developers only
if accepted by the GeoMoose Project Steering Committee.   A proposal
should be written to the PSC for new committers and voted on normally.  It
is not necessary to write an RFC document for these votes; email to 
geomoose-users is sufficient.

Removal of Git commit access should be handled by the same process.  

The new committer should have demonstrated commitment to GeoMoose and
knowledge of the GeoMoose source code and processes to the committee's
satisfaction, usually by reporting issues, submitting pull requests,
and/or actively participating in the various GeoMoose forums.

The new committer should also be prepared to support any new feature or
changes that he/she commits to the GeoMoose source tree in future
releases, or to find someone to which to delegate responsibility for
them if he/she stops being available to support the portions of code
that he/she is responsible for.  In the event no delegate is found to 
support the code, it will be subject to removal pending discussion by 
the PSC.  Each feature that falls into this situation will be handled 
on a case by case basis.

All committers should also be a member of geomoose-users mailing list
so they can stay informed on policies, technical developments and 
release preparation.


Committer Tracking
------------------

A list of all project committers will be managed in
https://github.com/geomoose/geomoose/blob/master/AUTHORS.rst with the
following format:

* Userid: the id that will appear in the Git commit logs for this person.

* Full name: the user's actual name. 

* Email address: A current email address at which the committer can be
  reached.  It may be altered in normal ways to make it harder to 
  auto-harvest. 

* A brief indication of areas of responsibility.  


Git Administrator
-----------------

Members of the Project Steering Committee will be designated as Git
Administrators.  That person will be responsible for giving Git commit
access to folks, updating the ``AUTHORS.rst`` file, and other Git related
management.

Initially, Dan Little and Jim Klassen will be the Git Administrators, changes
will be handled by regular PSC processes and recorded in ``AUTHORS.rst``.


Git Commit Practices
--------------------

The following are considered good Git commit practices for the GeoMoose
project: 

* Use meaningful descriptions for Git commit log entries.  Commit messages
  should follow Git commit conventions, i.e. a short one-line summary, followed
  by a blank line and a paragraph giving more detail.

* Add a GitHub issue reference like "(#1232)" as part of the commit
  message when possible.

* **Never** commit new features to a stable branch; only critical fixes. New
  features can only go in the main development master. This also applies
  to pre-release stable branches once they have been branched off of master.

* Discuss significant changes on the geomoose-users list before you
  make them. Larger changes require an RFC approved by the PSC.

* Ensure that all commits do not break any existing tests (or that
  the test suite be updated with expected results if required).

* Ensure that the committed code is in accordance with GeoMoose's coding
  conventions as per http://www.geomoose.org/developer/standards.html

* Ensure all source code in Git is in Unix text format as opposed to DOS
  text mode. 
  
* Use GitHub pull requests rather than directly committing to the
  branches as a practical way of testing proposed changes before inclusion.


Legal
-----

Committers are the front line gatekeepers to keep the code base clear of
improperly contributed code. It is important to the GeoMoose users,
developers and the OSGeo foundation to avoid contributing any code to the
project without it being clearly licensed under the project license.

Generally speaking the key issues are that those providing code to be included
in the repository understand that the code will be released under the
GeoMoose License, and that the person providing the code has the right
to contribute the code. For the committer themselves understanding about the
license is clear. For other contributors, the committer should verify
the understanding unless the committer is very comfortable that the contributor
understands the license (for instance frequent contributors).

If the contribution was developed on behalf of an employer (on work time, as
part of a work project, etc) then it is important that an appropriate
representative of the employer understand that the code will be contributed
under the GeoMoose License. The arrangement should be cleared with an
authorized supervisor/manager, etc.

The code should be developed by the contributor, or the code should be from a
source which can be rightfully contributed such as from the public domain, or
from an open source project under a compatible license.

All unusual situations need to be discussed and/or documented.

Committers should adhere to the following guidelines, and may be personally
legally liable for improperly contributing code to the source repository:

* Make sure the contributor (and possibly employer) is aware of the
  contribution terms.
* Code coming from a source other than the contributor (such as adapted
  from another project) should be clearly marked as to the original
  source, copyright holders, license terms and so forth. This information
  can be in the file headers, but should also be added to the project
  licensing file if not exactly matching normal project licensing
  (``geomoose/LICENSE``).
* Existing copyright headers and license text should never be stripped
  from a file. If a copyright holder wishes to give up copyright they
  must do so in writing to the Project Steering Committee before
  copyright messages are removed. If license terms are changed it has
  to be by agreement (written in email is ok) of the copyright
  holders.
* When substantial contributions are added to a file (such as substantial
  pull requests) the author/contributor should be added to the list of copyright
  holders for the file.
* If there is uncertainty about whether a change it proper to contribute
  to the code base, please seek more information from the project steering
  committee, or the foundation legal counsel. 


Voting History
--------------
Adopted on 6/27/2013 with PSC +1 votes from Eli Adam, Bob Basques, Brian Fischer, 
Brent Fraser, Jim Klassen.
