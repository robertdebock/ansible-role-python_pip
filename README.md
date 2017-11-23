ansible-role-python-pip
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-python-pip.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-python-pip)

Adds Pythons PIP to your system.

Requirements
------------

For Red Hat or CentOS systems this role required the EPEL repository to be available on RHEL/CentOS. robertdebock.epel can be used for that.
Other systems typically have the required packages in their repositories.
Adding the dependency robertdebock.epel only installs EPEL to Red Hat and CentOS systems, others will be skipped.

Role Variables
--------------

None known.

Dependencies
------------

- roberdebock.ansible-role-epel

Example Playbook
----------------

```
---
- hosts: all

  roles:
    - ansible-role-python-pip

  tasks:
    - name: install a pip package
      pip:
        name: ansible
        state: present
```

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
