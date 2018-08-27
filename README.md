python-pip
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-python-pip.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-python-pip)

Prepares your system to be able to use the ansible module "pip" by adding Pythons PIP.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/python-pip.png "Dependency")

Requirements
------------

For Red Hat or CentOS systems this role required the EPEL repository to be available on RHEL/CentOS. robertdebock.epel can be used for that.
Other systems typically have the required packages in their repositories.
Adding the dependency robertdebock.epel only installs EPEL to Red Hat and CentOS systems, others will be skipped.

Role Variables
--------------

- python_pip_modules: A list of pip modules to install.
- python_pip_version: The verion of pip to install
- python_pip_setuptools_version: The version of setuptools to install.

Dependencies
------------

No dependencies are set explicitly, but you can run these roles to prepare your system to use this role:

- [robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap)
- [robertdebock.buildtools](https://galaxy.ansible.com/robertdebock/buildtools) (For Alpine.)
- [robertdebock.epel](https://galaxy.ansible.com/robertdebock/epel) (For CentOS 7.)
- [robertdebock.scl](https://galaxy.ansible.com/robertdebock/scl) (For CentOS 6.)

Download the dependencies by issuing this command:

```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.4|ansible 2.5|ansible 2.6|
|------------|-----------|-----------|-----------|
|alpine-edge|yes|yes|yes|
|alpine-latest|yes|yes|yes|
|archlinux|yes|yes|yes|
|centos-6|yes|yes|yes|
|centos-latest|yes|yes|yes|
|debian-latest|yes|yes|yes|
|debian-stable|yes|yes|yes|
|fedora-latest|yes|yes|yes|
|fedora-rawhide|yes|yes|yes|
|opensuse-leap|yes|yes|yes|
|opensuse-tumbleweed|yes|yes|yes|
|ubuntu-artful|yes|yes|yes|
|ubuntu-latest|yes|yes|yes|

Example Playbook
----------------

```
---
- name: install ansible using pip for CentOS 7
  hosts: all

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.epel
    - role: robertdebock.python-pip
      python_pip_modules:
        - name: ansible
```

```
---
- name: install ansible using pip for CentOS 6
  hosts: all

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.scl
    - role: robertdebock.python-pip
      python_pip_modules:
        - name: ansible
```

```
---
- name: install ansible using pip for Alpine
  hosts: all

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.buildtools
    - role: robertdebock.python-pip
      python_pip_modules:
        - ansible
```

Install this role using `galaxy install robertdebock.python-pip`.

License
-------

Apache License, Version 2.0

Author Information
------------------

[Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
