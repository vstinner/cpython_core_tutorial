++++++++++++++++++++++++++++++++++++++++++++
Contribute to CPython: where should I start?
++++++++++++++++++++++++++++++++++++++++++++

CPython core isn't the easiest place to start. The development process is
rather enterprisy with long release cycles and rigid backwards compatibility
policy. CPython also support a lot of platforms and CPU architectures.

How can you start? Where? That's a hard question. CPython is old and widely
used: any change must be carefully discussed to remain Python homogeneous.
For bug fixes, the most complex part is the backward compatibility.

It's very hard to find "easy issue". First, just **watch** the current activity
to get some ideas.

* To start, the best is maybe to look at recent commits to see what is
  currently done to get some ideas:
  https://github.com/python/cpython/commits/master
* Look also at active bugs: see https://bugs.python.org/ homepage, and maybe
  the second and third pages
* You may also look at ideas currently discussed on the
  https://mail.python.org/mailman/listinfo/python-ideas mailing list

To find an easy issue, persistence is the key :-)

Contribute to CPython? What is CPython? CPython is made of many parts:

* CPython source code: basically made of 50% Python and 50% C code
* Build system: complex tools to build Python on all platforms, Visual
  Studio project for Windows
* Windows and macOS installer
* 233,000 lines of documentation written with Sphinx
* Documentation translated to multiple languages: french, japanese, and other
  languages
* Bug tracker: bugs.python.org which has its own "meta" bug tracker for bugs in
  the bug tracker :-)
* GitHub project: pull requests, host the Git repository
* Travis CI to run the test suite on Linux and check the documentation
* AppVeyor CI to run the test suite on Windows
* Buildbot master and many workers to run the test suite as post-commit on
  many variables architectures and operating systems

There are also many things around Python:

* Devguide: documentation of the CPython development workflow
* python-dev and python-committers mailing lists
* #python-dev IRC channel
* PyPI

Contributing to CPython is hard and it can take up to 2 years until your work
is released. Are you sure that CPython itself is the best project for you?
Depending on your interests and skills, you may enjoy better to contribute
to another popular project like Django or requests.

Contributing to CPython is harder because CPython developers require a very
high quality for contributions: every change must be carefully documented,
tested and implemented. The implementation can take several rounds until it
reaches the expected quality and respects a long list of requirements.

Ok, I understand and I am well aware of all these things. But I want to
contribute, how should I start?

* Bug triage: complete bug report to adjust the title, complete the
  description, identify impacted Python version and impacted platforms,
  help to reproduce the bug, or even help to analyze and find the **root bug**.

* Review pull requests: https://github.com/python/cpython/pulls/

  * Make sure that a change is carefully documented. For example, behaviour
    changes and enhancements must have the "..  versionchanged:: x.y" markup in
    the documentation of the module.
    New features must be have the ".. versionadded:: x.y" tag and maybe also
    documented in "What's New in Python X.Y?" documentation.
  * The NEWS entry and commit message must first explain the solved problem,
    then maybe explain the change itself. While the commit message can be
    technical and very detailed, the NEWS entry should be short and written
    for end-users who don't care of technical details.
  * Every change must be tested: exceptions are rare and should usually be
    justified. Example of exception which doesn't have to be justified: changes
    only impacting the documentation, changes fixing a typo in a comment.
  * The backward compatibility is very important. A change must be carefully
    reviewed to make sure that it doesn't break the backward compatibility.
    If it does break it, the change must be discussed with enough people
    to make sure that there is a smooth transition plan.
  * Feature removals require a DeprecationWarning in Python version N to remove
    it in version N+1. It's common that a feature is kept longer to avoid
    breaking the world just being a developer wants the perfection.
    Python developers must be pragmatic: balance between perfection and
    usability, very hard choices should be made and usually it takes a long
    to time to discuss them :-)
  * While Python 2 end of life is near (2020), Python 3 changes which make
    writing code working on Python 2 and Python 3 harder are usually rejected.

* Propose to write a bugfix change (a pull request) for an existing bug report.
  This task is very hard since usually if a bug report doesn't have a patch,
  it's because there is a disagreement on the bug itself, or because the bugfix
  is very hard to implement.
