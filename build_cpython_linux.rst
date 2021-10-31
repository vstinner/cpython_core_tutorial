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
  git@github.com:python/cpython.git`` which creates a ``cpython/`` directory.
  The history starts in 1991 so be patient, the clone can take several minutes!

* Get CPython dependencies:

  * Fedora:

    * version based on ``yum``::

        $ sudo yum install -y yum-utils
        $ sudo yum-builddep -y python3

    * version based on ``dnf``::

        $ sudo dnf install -y dnf-plugins-core
        $ sudo dnf builddep -y python3

  * Debian: ``sudo apt-get build-dep -y python3``

    .. note::

       If you can not install the dependencies of ``python3``, maybe you should
       check if you have a ``deb-src`` entry for your packages in
       ``/etc/apt/sources.list``.

  * Dependencies to get ``ssl`` and ``readline`` modules: OpenSSL headers
    (openssl-dev) and readline headers (libreadline-dev).

Build Python
------------

Single command::

    ./configure --with-pydebug && make

Or detailed instructions:

* Configuration Python in debug mode: ``./configure --with-pydebug``
* Build CPython: ``make``
* There is no need to install Python.

For example, with a missing dependency, the `make` command will show the optional modules which do not compile

.. code-block:: text

    The necessary bits to build these optional modules were not found:
    _lzma

In this case, you have to install the `xz` library. For Fedora 25 and 26, it's ``xz-devel``, but normally, this dependency is installed with ``builddep python3``. For Debian/Ubuntu, this dependency should be installed with ``apt-get build-dep python3``

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
