.. _build-cpython-macos:

Build CPython on macOS
======================

Guide written for brew.

See also :ref:`Build CPython on Linux <build-cpython-linux>`.

Get tools and dependencies
--------------------------

* `Install homebrew <https://brew.sh/>`_
* Install `Git <https://git-scm.com/>`_: ``brew install git``
* XXX install OpenSSL
* XXX install readline
* XXX install gcc, make, autotools?

Build CPython
-------------

Single command::

    ./configure --with-pydebug && make

Or detailed instructions:

* Configuration Python in debug mode: ``./configure --with-pydebug``
* Build CPython: ``make``
* There is no need to install Python.

XXX how to check "setup" output and detect missing dependencies?


Test Python
-----------

Test the Python REPL:

* Run Python: type ``./python.exe``.
* Import the ssl module: ``import ssl``. If the import works, you are good.
  Otherwise, you missed some dependencies.
* Exit Python

Run the test_os unit test::

    ./python -m test test_os

Expected output (something like this)::

    Run tests sequentially
    0:00:00 load avg: 0.51 [1/1] test_os
    1 test OK.

    Total duration: 2 sec
    Tests result: SUCCESS

If everything is fine, you are done! Let's move to the next section: XXX!

If something goes wrong, see :ref:`Getting Help <help>`.
