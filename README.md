# Description

Tutorial to contribute to the CPython project.

# Installation

You need to use a installed version of [Sphinx](https://www.sphinx-doc.org).

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

Once you have an installed version of [Sphinx](https://www.sphinx-doc.org), you can build the documentation.

```bash
make html
```

The result will be in `build/html/index.html`

You can check it via [http://localhost:8000](http://localhost:8000) if you run the following commands

```bash
cd build/html/
python3 -m http.server
```