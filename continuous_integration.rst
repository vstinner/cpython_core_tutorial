+++++++++++++++++++++++++++
Continuous Integration (CI)
+++++++++++++++++++++++++++

Travis CI
=========

XXX

Configuration: ``.travis.yml`` file.


AppVeyor
========

XXX

Configuration: ``.github/appveyor.yml`` file.


Buildbots
=========

* `python-buildbots mailing list
  <https://mail.python.org/mailman/listinfo/python-buildbots>`_
* `buildbot-status mailing list
  <https://mail.python.org/mm3/mailman3/lists/buildbot-status.python.org/>`_

CPython is running a `Buildbot <https://buildbot.net/>`_ server for continuous
integration, but tests are run as post-commit: see `Python buildbots
<https://www.python.org/dev/buildbot/>`_.

Buildbot "waterfall" views:

* `Python master ("3.x") <http://buildbot.python.org/all/waterfall?category=3.x.stable&category=3.x.unstable>`_
* `Python 3.6 <http://buildbot.python.org/all/waterfall?category=3.6.stable&category=3.6.unstable>`_
* `Python 3.5 <http://buildbot.python.org/all/waterfall?category=3.5.stable&category=3.5.unstable>`_
* `Python 2.7 <http://buildbot.python.org/all/waterfall?category=2.7.stable&category=2.7.unstable>`_

The buildbot configuration can be found in the `buildmaster-config project
<https://github.com/python/buildmaster-config/>`_ (start with the
``master/master.cfg`` file).

