Build CPython on Windows
========================

Guide to build the master branch of CPython. Other Python versions need
a different Visual Studio version.

To develop on CPython, the best is to enable all debug checks and so compile
Python in "debug mode".

Install tools and dependencies
------------------------------

* Install `Visual Studio 2017 <https://www.visualstudio.com/>`_
* Install `Git <https://git-scm.com/>`_:
  `Download Git for Windows <https://git-scm.com/download/win>`_
* Open a terminal: run ``cmd.exe``
* Go the Python directory
* Download source code of dependencies (OpenSSL, Tk, etc.):
  type ``PCbuild\get_externals.bat``

Build CPython in the IDE
------------------------

* Open Visual Studio
* Open ``PCbuild/pcbuild.sln`` solution
* Select ``Debug`` and ``x64`` (64-bit)
* Right click on the solution: Build, or just "F10"
* Close Visual Studio

Build CPython in the command line
---------------------------------

* Open a terminal (like ``cmd.exe``)
* Type: ``PCbuild\build.bat -e -d -p x64``

  * ``-e``: download external dependencies (OpenSSL, Tkinter, ...)
  * ``-d``: build in debug mode (``Py_DEBUG``, enable assertions, ...)
  * ``-p x64``: build in 64-bit mode

Run Python
----------

* Open a terminal: run ``cmd.exe``
* Go to the Python directory
* Run ``PCbuild\amd64\python_d.exe``
* Try to import the ``ssl`` module: ``import ssl``. If the ssl module is
  available, you are good. Otherwise, you missed maybe the "get_externals.bat"
  step?

Your ``python_d.exe`` works? Great! Let's move to the next section.
