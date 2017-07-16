Build CPython on Windows
========================

Guide to build the master branch of CPython. Other Python versions need
a different Visual Studio version.

To develop on CPython, the best is to enable all debug checks and so compile
Python in "debug mode".

Install tools and dependencies
------------------------------

* Install `Visual Studio 2015 <https://www.visualstudio.com/>`_: XXX
* Install `Git <https://git-scm.com/>`_:
  `Download Git for Windows <https://git-scm.com/download/win>`_
* Open a terminal: run ``cmd.exe``
* Go the Python directory
* Download source code of dependencies (OpenSSL, Tk, etc.):
  type ``PCbuild\get_externals.bat``

Build CPython
-------------

* Open Visual Studio
* Open ``PCbuild/pcbuild.sln`` solution
* Select ``Debug`` and ``x64`` (64-bit)
* Right click on the solution: Build, or just "F10"
* Close Visual Studioo

Run Python
----------

* Open a terminal: run ``cmd.exe``
* Go to the Python directory
* Run ``PCbuild\amd64\python_d.exe``
* Try to import the ``ssl`` module: ``import ssl``. If the ssl module is
  available, you are good. Otherwise, you missed maybe the "get_externals.bat"
  step?

Your ``python_d.exe`` works? Great! Let's move to the next section.
