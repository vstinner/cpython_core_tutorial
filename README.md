# Description

Tutorial to contribute to the CPython project.

# Design and goal of the tutorial

The final goal is to train contributors to promote them to CPython core
developers. That's the long term goal.

The short term goal is to fill the gap in the current devguide between
"compile/install python" and "congrats! you are now a CPython core developer!".
Document all the things expected to be known to become a core developer.

# Gamification

* Give badges once a quest is complete
* Use existing https://openbadges.org/ infra?
* Different levels of badges?

  * Big serious badges, maybe even publics, for major contributions.
    For example, an accepted PEP. -- use openbadges for this?
  * Minor badges, maybe kept private, not validated by third party like a
    mentor. The student validates its own progress on clicking "I completed the
    exercice". It's just a tool to make the tutorial more fun.

* Personal but private statistics, account the number of:

  * PR: proposed, rejected, accepted (merged)
  * Emails sent
  * Bugs: open, fixed, rejected
  * Comments on bugs
  * Reviews on PR
  * XXX it may be difficult to account contributions on old CPython tools
   like Rietveld (old reviewing system), Mercurial where the contributor
   was not always mentionned, Subversion/CVS, etc.

# Installation

You need to use a installed version of [Sphinx](http://www.sphinx-doc.org/en/stable/).

For that, you have two options. Firstly, use the sphinx package from your favorite distribution

## Fedora

```bash
dnf install python-sphinx
```

## Debian/Ubuntu

```bash
apt-get install python3-sphinx
```


# Compilation

Once you have an installed version of [Sphinx](http://www.sphinx-doc.org/en/stable/), you can build the documentation.

```bash
make html
```

The result will be in `build/html/index.html`

You can check it via [http://localhost:8000](http://localhost:8000) if you run the following commands

```bash
cd build/html/
python3 -m http.server
```
