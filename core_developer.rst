+++++++++++++++++++++++++++++++++
What is a CPython core developer?
+++++++++++++++++++++++++++++++++

Devguide: `How to Become a Core Developer
<https://devguide.python.org/coredev/>`_

See `[python-committers] What is a CPython core developer?
<https://mail.python.org/pipermail/python-committers/2017-September/004865.html>`_
(Sept 2017).

python-committers
=================

While the `python-committers mailing list
<https://mail.python.org/mailman/listinfo/python-committers>`_ is public
(anyone can be archives), only core developers are allowed to subscribe and to
send messages.

Who are core developers?
========================

* `Devguide Developer Log <https://devguide.python.org/developers/>`_
* `GitHub contributors statistics
  <https://github.com/python/cpython/graphs/contributors>`_ gives an idea of
  which core developers were active recently: click on the graph to select a
  recent period, like last 6 months

Different stages of core developers
===================================

* Newcomer
* Contributor: as soon as you post a comment, send an email, ask a question,
  you become an active contributor!
* :ref:`Permission for bug triage <triage>`: once peers estimated that your
  behaviour is correct and that you are active, you may be proposed to be
  promoted to "bug triage"
* :ref:`Followed by a mentor <menthor>`: spotted active contributors can be asked to get a
  mentor to speedup their learning
* :ref:`Core developer <core-dev>`, allowed to merge a pull request: once other core developers
  consider that a contributor is ready to be promoted, a core dev opens
  a vote on python-committers

New powers but also new responsabilities
========================================

The main power of a core developer is to be allowed to merge a pull request.

New powers comes with new responsabilities. Merging a pull request indirectly
means becoming responsible of the added and modified code.

.. _triage:

Bug tracker
===========

See `Helping Triage Issues <https://devguide.python.org/tracker/#helptriage>`_
and `Triaging an Issue <https://devguide.python.org/triaging/>`_.

Requirements to get the bug triage permission
---------------------------------------------

Requirements:

* Be nice, polite and respectful
* Know what they are talking about, and explain their reasoning well.
  Contributions to the bug tracker that demonstrate an understanding of our
  code culture...specifically, commenting that a bug should be closed (and why)
  and demonstrating an understanding of what python versions a bug applies to
  (enhancement versus bug fix, when to backport a bug fix and when not).  See
  the `Status of Python branches
  <https://devguide.python.org/#status-of-python-branches>`_
* Don't close a bug if it's not well understood to not "loose" information
  (closed bugs are ignored in search by default, and hidden from the main
  page).

A good triager must be familiar with our codebase, our bug tracker,
and our "code culture", in particular:

* being able to find (or remember) duplicate and related issues, link
  them to each other, and closing the duplicates as necessary;
* being able to correctly select the versions affected by the issue,
  the components, the stage, and other fields;
* being able to verify if the issue can be reproduced and if the
  report is valid or not;
* being able to recognize commonly reported issues and link to the
  appropriate FAQ or other existing issues/explanations;
* being able to identify and specify the next step, possibly
  suggesting which files should be updated to fix the issue;
* being able to locate the commits that might have introduced the
  issue, and the reason for the change;
* being able to leave meaningful opinions on the issue (e.g. whether
  it should be addressed or closed and why);

It usually takes some time and a few contributions before people can
do these things.

Responsability for bug tracker:

* Request more information if a report is incomplete
* Ping original reporters if they don't reply
* Adjust Python version, component, bug type, etc.
* Rewrite the issue title if needed
* Close duplicated bugs as DUPLICATE
* Close irrevelant bugs as NOTABUG

Nice to have, but not a strong requirement:

* Signed the CLA
* At least one commit merged into CPython


Give bug triage permission to a contributor
-------------------------------------------

A core developer has to identify an active contributor on the bug tracker, or a
contributor can also ask for more power themselves.

If the contributor reachs the requirements listed in the previous section, the
core developer give them triage.

.. _menthor:

Mentoring
=========

XXX see :ref:`Getting help <help>`.


.. _core-dev:

Requirements to become a core developer
=======================================

The historical definition is that CPython core developer has the *commit bit*,
is able to push a change to *upstream*, to the `GitHub cpython project
<https://github.com/python/cpython/>`_.

Officially, other core developers don't expect and cannot expect anything from
a developer.

The unwritten definition is that other core developers expect from a core
developer to maintain their contributions: long term *commitement*, since
CPython requires long term support: 5 years or longer. If a core developer
writes a new large chunk of code but then disappears for whatever reasons,
there is a risk that the code dies slowly.

For example, Python branches are supported for 5 years. See the `Status of
Python branches
<https://docs.python.org/devguide/#status-of-python-branches>`_.

Most of the following core developer requirements are already expected from
regular contributors.

Be nice and respectful
----------------------

Know to be nice and respectful to the others, at least to the extent
they're nice and respectful to yourself :-)  We don't have a rock-star (or
"bro", "wizard", "ninja", whatever the hyperbole of the day is) culture here.

Humility
--------

Show a bit of humility towards existing work and try to understand the
decisions behind something before deciding to change it all.  That said,
given Python's current position on the technical evolution and adoption
curve, we get less and less proposals for sweeping changes (perhaps not
enough, actually, since even when rejected, they help challenge the status
quo).

Long term commitement
---------------------

When someone lands a big chunk of code, we need someone to maintain it for at
least the next 2 years. Maybe for the next 10 years.

It is not strictly a requirement, it's more a whish from other core developers.

Reviews
-------

Review patches and pull requests. While we don't require not expect
newcomers to review, we expect that core developers dedicate a part of their
time on reviews. What it means is that core developers care about the quality
of the whole code base (and also the non-code parts), not only their own
contributions to it.

CPython workflow
----------------

Know the CPython workflow. Be aware of the pre-commit and
post-commits CIs. How ideas are discussed. It's not only about writing and
pushing patches. This part is also required from regular contributors, at
least the experienced ones.

CPython lifecycle
-----------------

Know the project's lifecycle: Python has multiple maitained branches, some of
them accept bugfixes, others only security fixes. Deciding if a fix can or
cannot be backported is a complex question.

Python C API specific issues
----------------------------

For C developer: know CPython specific issues like reference leaks.

Good quality patches
--------------------

Good quality patches: proposed changes are good (or almost good) at the first
iteration. Or, if the code isn't good at the first iteration, the author is
able to figure it out by themselves and doesn't rush merge it.  Of course,
nobody is perfect, which is why non-trivial code written by core developers
ideally goes through a review phase anyway. But a general sense of what is
"in good state for review/merging" vs. "just a draft I'm working on" is
indeed preferrable.

Maintain pushed code
--------------------

Pushing core means becoming responsible for this code. For
regressions, backward compatibility, security, etc.

Backward compatibility
----------------------

CPython has a long history and many unwritten strict rules. For example,
backward compatibility is taken very seriously. We don't remove public
functions in a minor release (3.x), but start with a deprecation period. It's
not only about removing features, but also *changing* the behaviour. Even if
Python has a wide test suite with a good code coverage, some functions are
still untested, or not fully tested.

Be patient
==========

Be patient, being aware of Python complex code and workflow can take between 6
months and 2 years.

Vote to promote a contributor as a core developer
=================================================

Identify a potential candidate
------------------------------

Usually the contributor doesn't ask for themselves to become a core developer,
but another core developer proposes to promote them.

The main questions about a potential new core developer are:

* Would gaining core developer privileges improve their ability to contribute
  effectively (in my opinion or the opinion of another core developer)?

* Do a core developer that is willing to mentor them trust their judgment on
  when things should be escalated for further review & discussion (or even
  rejected outright) versus just going ahead and merging them?

Ask the candidate permission
----------------------------

The first step is to ask the contributor if they want to become a core
developer. Since great power comes with great responsibilities, it's not
uncommon that some contributors prefer to remain contributors. Technically, it
doesn't prevent to propose pull requests, reviews, etc.

Private vote
------------

If the contributor agrees, usually a *private* discussion starts. Sadly, the
discussion is private because it's tricky to discuss someone skills in public.
A negative vote can be harmful, whereas it isn't the intend.

Sometimes, the contributor is evaluated as "too green" and someone can propose
to become their mentor to help them to learn the workflow, give advices on pull
requests, etc.

Public vote
-----------

The real vote occurs on the python-committers list where only core developers
are allow to post. The developer who proposes to promote someone has to write a
very short biography, list previous contributions and evaluates the contributor
skills.

A negative vote can still happen at this point. It doesn't mean that the
contributor will never become a core dev, just that they need more practice.

Vote result
-----------

If the vote is positive, the contributor sends their SSH key and will be
subscribed to the python-committers mailing list.

Examples of public votes
------------------------

* `Proposing Carol Willing to become a core developer
  <https://mail.python.org/pipermail/python-committers/2017-May/004519.html>`_
  (Brett Cannon, May 2017)
* `Proposed new core developer -- Mariatta Wijaya
  <https://mail.python.org/pipermail/python-committers/2017-January/004175.html>`_
  (Raymond Hettinger, January 2017)
* `Promote Xiang Zhang as a core developer
  <https://mail.python.org/pipermail/python-committers/2016-November/004045.html>`_
  (Victor Stinner, Nov 2016)
* `commit privileges for INADA Naoki
  <https://mail.python.org/pipermail/python-committers/2016-September/004013.html>`_
  (Yury Selivanov, Sept 2016)

Other votes:

* `commit privs given to Maciej Szulik for bugs.python.org work
  <https://mail.python.org/pipermail/python-committers/2016-December/004121.html>`_
  (Brett Cannon, December 2016): https://hg.python.org/tracker/ repository

Gaining Commit Privileges
-------------------------

See `DevGuide: Gaining Commit Privileges
<https://devguide.python.org/coredev/#gaining-commit-privileges>`_.


We Are All Volunteers
=====================

Except one or two exceptions, no core developer is paid to contribute to
CPython: *we are all volunteers*. Don't be surprised to not get any kind of
feedback in next hours, or sometimes even before one week.

Most core developers have a specific interest in specific areas of the code,
and so not all core developers are interested by your specific issue.

