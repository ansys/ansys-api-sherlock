### ansys-api-sherlock gRPC Interface Package

This Python package contains the auto-generated gRPC Python interface files for
Sherlock.


#### Installation

Provided that wheels have been published to public PyPI, you can install the latest package
with this command:

```
pip install ansys-api-sherlock
```

Otherwise, in the PySherlock documentation, see the instructions for downloading and installing
this package in`Install packages <https://sherlock.docs.pyansys.com/version/dev/getting_started/installation.html>`_.


#### Build packages

To build the gRPC packages, run these commands:

```
pip install build
python -m build
```

The preceding commands create both the source distribution containing only the PROTO files
and the wheel containing the PROTO files and build Python interface files.

Note that the interface files are identical regardless of the version of Python
used to generate them, but the last pre-built wheel for ``grpcio~=1.17`` was
Python 3.7. To improve your build time, use Python 3.7 when building the
wheel.


#### Manual deployment

After building the packages, manually deploy them with these commands:

```
pip install twine
twine upload dist/*
```

Note that this is automatically done through CI/CD.


#### Automatic deployment

This repository contains a ``.github`` directory with the ``ci.yml`` workflow
file. This file uses GitHub Actions to automatically build the
source and wheel packages for these gRPC Python interface files. By default,
these are built on PRs, the main branch, and on tags when pushing. Artifacts
are uploaded for each PR.

To publicly release wheels to PyPI, ensure that your branch is up to date and then
push tags. For example, to push tags for version ``v0.5.0``, you would use these commands:

```bash
git tag v0.5.0
git push --tags
```
