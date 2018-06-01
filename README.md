python-pip
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-python-pip.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-python-pip)

Prepares your system to be able to use the ansible module "pip" by adding Pythons PIP.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/robertdebock.github.io/artifacts/python-pip.png "Dependency")

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

No dependencies are set explicitly, but you can run these roles to prepare your system to use this role:

- robertdebock.bootstrap
- robertdebock.buildtools
- robertdebock.epel
- robertdebock.scl

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.3|ansible 2.4|ansible 2.5|
|------------|-----------|-----------|-----------|
|alpine-3.6|yes|yes|yes|
|alpine-3.7|yes|yes|yes|
|archlinux|no|no|no|
|centos-6|no|no|no|
|centos-7|yes|yes|yes|
|debian-buster|yes|yes|yes|
|debian-stretch|yes|yes|yes|
|debian-wheezy|no|no|no|
|fedora-27|yes|yes|yes|
|fedora-28|yes|yes|yes|
|opensuse-42.2|yes|yes|yes|
|opensuse-42.3|yes|yes|yes|
|ubuntu-artful|yes|yes|yes|
|ubuntu-bionic|yes|yes|yes|

Example Playbook
----------------

```
---
- hosts: all

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.buildtools
    - role: robertdebock.epel
    - role: robertdebock.scl
    - role: robertdebock.python-pip
      python_pip_modules:
        - name: ansible
        - version: 2.4.2.0
```

Install this role using `galaxy install robertdebock.python-pip`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
