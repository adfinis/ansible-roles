=============
Ansible Roles
=============

Ansible roles to manage your infrastructure in an automated and reproducable
way.

Features
========
The goal of this repository is to provide a fully blown Ansible roles set to
manage your infrastructure in an automated fashion whilst providing full
reproducability.

All roles support at least the following distributions:

* Debian 7 & 8
* Ubuntu 14.04 & 16.04
* Centos 6 & 7

In addition the roles take care of the necessary SELinux configuration if
required.

Requirements
============
In order to use the roles please make sure to fulfill the following
requirements:

* FQDN configured on the target host
* Ansible 2.0+ is used

Installation
============
Below the required steps to include the roles into your playbooks and projects:

1. Clone this repository

TODO

Roles
=====
Currently the repository features the following roles:

+------+-------------------+
| Role | Description       |
+======+===================+
| ntp  | manage ntp server |
+------+-------------------+

Structure
=========

TODO

Contributions
=============
Contributions are more than welcome! Please feel free to open new issues or
pull requests.

License 
=======
GNU GENERAL PUBLIC LICENSE Version 3

See the `LICENSE`_ file.

.. _LICENSE: LICENSE
