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
any given version of Python, so far Python 2.6, 2.7 and 3.5 are supported.

Adding support for any other version should be trivial though,
so pull requests are always welcome.

Requirements
============
None

Role Variables
==============
* python_26: ``true/false`` (defaults to **false**)
* python_27: ``true/false`` (defaults to **true**)
* python_35: ``true/false`` (defaults to **true**)

Dependencies
============
Ubuntu 14.04 (trusty)

Example Playbook
================
::

    - hosts: servers
      roles:
        - role: gforcada.compile-python
      vars:
        - python_26: true
        - python_27: true
        - python_35: true

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

