.. _build-cpython-linux:

Build CPython on Linux
======================

See also :ref:`Build CPython on macOS <build-cpython-macos>` for specific
instructions for macOS.

Get tools and dependencies
--------------------------

* Install `Git <https://git-scm.com/>`_:

  * Fedora: ``sudo dnf install -y git-core``
  * Debian: ``sudo apt-get install -y git-core``

* Clone the `GitHub cpython project <https://github.com/python/cpython/>`_: ``git clone
  https://github.com/python/cpython.git`` which creates a ``cpython/`` directory.
  The history starts in 1991 so be patient, the clone can take several minutes!

* Get CPython dependencies:

  * Fedora: ``sudo yum-builddep python3``
  * Debian: ``sudo apt-get build-dep python3``
  * Dependencies to get ``ssl`` and ``readline`` modules: OpenSSL headers
    (openssl-dev) and readline headers (libreadline-dev).

* XXX install gcc, make, autotools?

Build Python
------------

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

* Run Python: type ``./python``
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
