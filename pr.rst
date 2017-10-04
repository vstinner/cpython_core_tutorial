+++++++++++++++++++++++++++++
Write your first Pull Request
+++++++++++++++++++++++++++++

Create your GitHub account
==========================

If you already have a GitHub account, skip this section ;-)

* https://github.com/
* Click on [Sign up]
* Fill the form
* XXX
* Confirm your email
* XXX


Link your bugs.python.org account to your GitHub account
========================================================

* Go to your bugs.python.org account
* Go to "Your Details"
* Set the **GitHub name** field
* Submit your changes


Sign the CLA
============

Sign the Python Contributor Agreement.

* Sign https://www.python.org/psf/contrib/contrib-form/
* Wait... the confirmation is done manually by humans, so be prepared to wait
  up to one week (usually 3 business days)

For legal question, you can send an email to `legal@python.org <mailto:legal@python.org>`_ .


Create a local Git branch
=========================

Once you have your patch (see XXX Python or XXX C fix sections), make sure that
your changes are in a local branch::

    git checkout -b mybranch

Template of a commit message::

    bpo-12345: fix a bug in the email module

    Fix a race condition in the email module. Before xxx failed. It now works
    well!


Git remotes
===========

* origin: your repository
* upstream: cpython/python


Publish your pull request
=========================

Manually
--------

* git push origin HEAD
* Open https://github.com/python/cpython and click on "New pull request"
* Select the base fork: ``python/cpython`` and base branch: ``master``
* Select the head fork: ``<username>/cpython`` and base branch: the branch
* Press ``Create Pull Request`` button

For more information: please, you could read `this section <https://devguide.python.org/gitbootcamp/#creating-a-pull-request>`_ of the devguide
