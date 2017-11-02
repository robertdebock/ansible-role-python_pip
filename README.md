Role Name
=========

Have Pythons PIP available.

Requirements
------------

This role required the EPEL repository to be available. robertdebock.epel can be used for that.

Role Variables
--------------

None known.

Dependencies
------------

- roberdebock.epel

Example Playbook
----------------

```
---
- hosts: servers
  roles:
    - python-pip

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
