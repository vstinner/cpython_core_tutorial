What is a CPython core developer?
=================================

Devguide: `How to Become a Core Developer
<https://devguide.python.org/coredev/>`_

python-committers
-----------------

While the `python-committers mailing list
<https://mail.python.org/mailman/listinfo/python-committers>`_ is public
(anyone can be archives), only core developers are allowed to subscribe and to
send messages.

Who are core developers?
------------------------

* `Devguide Developer Log <https://devguide.python.org/developers/>`_
* `GitHub contributors statistics
  <https://github.com/python/cpython/graphs/contributors>`_ gives an idea of
  which core developers were active recently: click on the graph to select a
  recent period, like last 6 months

Requirements to become a core developer
---------------------------------------

The historical definition is that CPython core developer has the *commit bit*,
is able to push a change to *upstream*, to the `GitHub cpython project
<https://github.com/python/cpython/>`_.

Officially, other core developers don't expect and cannot expect anything from
a developer.

The unwritten definition is that other core developers expect from a core
developer to maintain his/her contributions: long term *commitement*, since
CPython requires long term support: 5 years or longer. If a core developer
writes a new large chunk of code but then disappears for whatever reasons,
there is a risk that the code dies slowly.

For example, Python branches are supported for 5 years. See the `Status of
Python branches
<https://docs.python.org/devguide/#status-of-python-branches>`_.

* Long term commitement
* Review patches and pull requests
* Know the CPython workflow
* For C developer: know Python specific issues like reference leaks (and the
  garbage collector)
* Good quality patches: proposed changes are good (or almost good) at the first
  iteration

CPython has a long history and many unwritten strict rules. For example,
backward compatibility is taken very seriously. We don't remove public
functions in a minor release (3.x), but start with a deprecation period. It's
not only about removing features, but also *changing* the behaviour. Even if
Python has a wide test suite with a good code coverage, some functions are
still untested, or not fully tested.

Be patient, being aware of Python complex code and workflow can take between 6
months and 2 years.

Bug triage
----------

Contributors active on the bug tracker are sometimes proposed to get the right
to "triage" the bug tracker, like closing issues.

Vote to promote a contributor as a core developer
-------------------------------------------------

Usually the contributor doesn't ask himself/herself to become a core developer,
but another core developer proposes to promote him/her.

The first step is to ask the contributor if he/she wants to become a core
developer. Since great power comes with great responsabilities, it's not
uncommon that some contribtors prefer to remain contributors. Technically, it
doesn't prevent to propose pull requests, reviews, etc.

If the contributor agrees, usually a *private* discussion starts. Sadly, the
discussion is private because it's tricky to discuss someone skills in public.
A negative vote can be harmful, whereas it isn't the intend.

Sometimes, the contributor is evaluated as "too green" and someone can propose
to become his mentor to help him to learn the workflow, give advices on pull
requests, etc.

The real vote occurs on the python-committers list where only core developers
are allow to post. The developer who proposes to promote someone has to write a
very short biography, list previous contributions and evaluates the contributor
skills.

A negative vote can still happen at this point. It doesn't mean that the
contributor will never become a core dev, just that he/she needs more practice.

If the vote is positive, the contributor sends his/her SSH key and will be
subscribed to the python-committers mailing list.

Examples of votes:

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

We Are All Volunteers
---------------------

Except one or two exceptions, no core developer is paid to contribute to
CPython: *we are all volunteers*. Don't be surprised to not get any kind of
feedback in next hours, or sometimes even before one week.

Most core developers have a specific interest in specific areas of the code,
and so not all core developers are interested by your specific issue.

