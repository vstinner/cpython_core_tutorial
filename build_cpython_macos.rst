.. _build-cpython-macos:

Build CPython on macOS
======================

Guide written for brew.

See also :ref:`Build CPython on Linux <build-cpython-linux>`.

Get tools and dependencies
--------------------------

* Run ``sudo xcode-select --install`` to install the XCode Command Line Tools,
  which includes compilers and ``make``
* `Install homebrew <https://brew.sh/>`_
* Install `Git <https://git-scm.com/>`_: ``brew install git``
* Install OpenSSL: ``brew install openssl``
* Install readline: ``brew install readline``
* Clone the `GitHub cpython project <https://github.com/python/cpython/>`_: ``git clone
  https://github.com/python/cpython.git`` which creates a ``cpython/`` directory.
  The history starts in 1991 so be patient, the clone can take several minutes!

Build CPython
-------------

Single command (copy and paste the whole thing, including backslashes!)::

    PKG_CONFIG_PATH="$(brew --prefix openssl)/lib/pkgconfig" \
    CPPFLAGS="-I$(brew --prefix readline)/include" \
    LDFLAGS="-L$(brew --prefix readline)/lib" \
    ./configure --with-pydebug \
    && make

Or, in separate steps:

* Tell Python where to find the libraries you installed with Homebrew::

    export PKG_CONFIG_PATH="$(brew --prefix openssl)/lib/pkgconfig"
    export CPPFLAGS="-I$(brew --prefix readline)/include"
    export LDFLAGS="-L$(brew --prefix readline)/lib"

* Configure Python in debug mode: ``./configure --with-pydebug``
* Build CPython: ``make``
* There is no need to install Python.


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
