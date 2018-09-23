.. -*- coding: utf-8 -*-

==============
Compile python
==============
Usually you don't want to mess with system packages,
specially if the package in question is python.

Distributions usually patch python in a way that may not work together with your app.

On those occasions rather than replacing the version provided by your distribution is usually better to compile your own.

*And that's what this ansible playbook is for!*

Installs all necessary tools to build and install Python and then installs
any given version of Python.

So far Python 2.4, 2.6, 2.7, 3.1, 3.2, 3.3, 3.4, 3.5, 3.6 and 3.7 are supported,
plus installing system dependencies to install (not done in this role):

- pillow
- lxml

If other versions are wanted,
pull requests welcome.

For ease of usage an easy to remember symlinks are provided for each python version,
i.e. ``/srv/python27``, ``/srv/python36`` and so on.

Requirements
============
None

Role Variables
==============
* python_24: ``true/false`` (defaults to **false**)
* python_26: ``true/false`` (defaults to **false**)
* python_27: ``true/false`` (defaults to **true**)
* python_31: ``true/false`` (defaults to **false**)
* python_32: ``true/false`` (defaults to **false**)
* python_33: ``true/false`` (defaults to **false**)
* python_34: ``true/false`` (defaults to **false**)
* python_35: ``true/false`` (defaults to **false**)
* python_36: ``true/false`` (defaults to **true**)
* python_37: ``true/false`` (defaults to **false**)
* pillow: ``true/false`` (defaults to **false**)
* lxml: ``true/false`` (defaults to **false**)

Dependencies
============
Ubuntu 14.04 (trusty)
Ubuntu 16.04 (xenial)
Ubuntu 18.04 (bionic)

.. note::
   to run the role on *xenial* one first needs to ssh into the virtual machine and install python, i.e.:
   ``sudo apt-get install python``.

Example Playbook
================
::

    - hosts: servers
      roles:
        - gforcada.compile-python
      vars:
        - python_26: true
        - python_27: true
        - python_36: true

There is an example ``Vagrantfile`` to test it locally.

License
=======
BSD

Author Information
==================
Gil Forcada Codinachs

Contribute
==========
Code can be found at: https://github.com/gforcada/ansible-compile-python

Please report issues at: https://github.com/gforcada/ansible-compile-python/issues

