.. flake8-profiles documentation master file, created by
   sphinx-quickstart on Sat Jan  4 17:42:51 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

flake8-profiles: Configurable defaults for flake8
=================================================

flake8-profiles is a :mod:`flake8` plugin that lets you manage default
flake8 configurations for multiple projects.

With flake8-profiles, you can write a set of default configurations in
one place, then choose from those profiles for each project. You can
use directives like ``extend-ignore`` to further customize a profile
for a specific project.

.. toctree::
    :hidden:
    :maxdepth: 2

    index

Installation
------------

.. code-block:: bash

    pip install flake8-profiles

Usage
-----

You will need a directory containing your profiles. For example::

    config
    ├── default.conf
    └── nodoc.conf

Each profile file should be a valid :mod:`flake8` config file::

    [flake8]
    ignore = D107

When you run :program:`flake8`, set the environment variable
:envvar:`FLAKE8_PROFILES_DIR` to locate this directory::

    FLAKE8_PROFILES_DIR=config flake8

Then, pass :option:`--profile` to select one of the profiles::

    FLAKE8_PROFILES_DIR=config flake8 --profile nodoc

Bugs
----

Please report any bugs to the `issue tracker
<https://github.com/twosigma/flake8-profiles/issues>`_.
