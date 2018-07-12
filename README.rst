=============
ANSIBLE ROLES
=============

This repository is deprecated. There is a repository per role on our `GitHub page <https://github.com/adfinis-sygroup>`_ and those are also available via `Ansible Galaxy <https://galaxy.ansible.com/adfinis-sygroup/>`_.
=========================================================================================================================================================================================================================

.. image:: https://img.shields.io/github/license/adfinis-sygroup/ansible-roles.svg?style=flat-square
  :target: https://github.com/adfinis-sygroup/ansible-roles/blob/master/LICENSE

.. image:: https://img.shields.io/travis/adfinis-sygroup/ansible-roles.svg?style=flat-square
  :target: https://github.com/adfinis-sygroup/ansible-roles

Ansible roles to manage your infrastructure in an automated and reproducible
way.


FEATURES
========
The goal of this repository is to provide a fully blown Ansible roles set to
manage your infrastructure in an automated fashion whilst providing full
reproducibility.

All roles support at least the following distributions:

* Debian 7 & 8 & 9
* Ubuntu 14.04 & 16.04
* Centos 6 & 7

In addition the roles take care of the necessary SELinux configuration if
required.


REQUIREMENTS
============
In order to use the roles please make sure to fulfill the following
requirements:

* FQDN configured on the target host
* Ansible 2.0+ is used


INSTALLATION
============
Below the required steps to include the roles into your playbooks and projects:

1. Create a project directory (git repository with playbooks, roles,
   group\_vars and/or host\_vars)
#. Add this repository as a git submodule
   (``git submodule add https://github.com/adfinis-sygroup/ansible-roles.git
   adfinis-roles``)
#. Configure Ansible to use the additional roles path

.. code-block:: Ini

  [defaults]
  ansible_managed     = Warning: File is managed by Ansible [https://github.com/adfinis-sygroup/ansible-roles.git]
  retry_files_enabled = False
  hostfile            = ./hosts
  roles_path          = ./adfinis-roles

4. Create your own project specific roles in the directory ``roles``, Ansible
   will use both directories (with precedence of ``roles``).


ROLES
=====
Currently the repository features the following roles:

+---------------+-----------------------------------------------------------+
| Role          | Description                                               |
+===============+===========================================================+
| ansible       | install base packages and Ansible related packages        |
+---------------+-----------------------------------------------------------+
| console       | manage standard tools, bashrc and vimrc                   |
+---------------+-----------------------------------------------------------+
| grub          | install and configure grub                                |
+---------------+-----------------------------------------------------------+
| hostname      | set system hostname                                       |
+---------------+-----------------------------------------------------------+
| hwraid        | hardware raid controller management tools                 |
+---------------+-----------------------------------------------------------+
| hw_vm_tools   | install hardware and virtual machine tools, like guest    |
|               | tools for virtual machine hypervisors                     |
+---------------+-----------------------------------------------------------+
| ipmi          | Manage IPMI devices                                       |
+---------------+-----------------------------------------------------------+
| iptables      | install iptables persistent services and configure        |
|               | iptables rules                                            |
+---------------+-----------------------------------------------------------+
| locales       | configure system locales and keyboard configuration       |
+---------------+-----------------------------------------------------------+
| mariadb       | manage a mariadb server and client (if mariadb is not     |
|               | available, mysql will be installed instead)               |
+---------------+-----------------------------------------------------------+
| motd          | set the MOTD                                              |
+---------------+-----------------------------------------------------------+
| network       | manage network interfaces and IP addresses and routes     |
+---------------+-----------------------------------------------------------+
| nginx         | install and manage nginx                                  |
+---------------+-----------------------------------------------------------+
| nodejs        | install nodejs on a server                                |
+---------------+-----------------------------------------------------------+
| ntp           | manage ntp client and server                              |
+---------------+-----------------------------------------------------------+
| pkg_mirror    | manage system package sources                             |
+---------------+-----------------------------------------------------------+
| pki           | PKI related stuff, like generate certificates and         |
|               | diffie-hellman parameters                                 |
+---------------+-----------------------------------------------------------+
| postfix       | manage postfix to send and receive email                  |
+---------------+-----------------------------------------------------------+
| rpcbind       | manage rpcbind package and service                        |
+---------------+-----------------------------------------------------------+
| rsyslog       | install and configure rsyslog                             |
+---------------+-----------------------------------------------------------+
| snmp          | manage snmp server and client                             |
+---------------+-----------------------------------------------------------+
| ssh           | manage ssh server and client                              |
+---------------+-----------------------------------------------------------+
| telegraf      | install telegraf and create configurations                |
+---------------+-----------------------------------------------------------+
| upgrade       | install dist upgrades                                     |
+---------------+-----------------------------------------------------------+
| users         | manage POSIX users and groups                             |
+---------------+-----------------------------------------------------------+


CONTRIBUTIONS
=============
Contributions are more than welcome! Please feel free to open new issues or
pull requests.

We have some contribution rules:

* Each change, regardless if it's a new role, a bug fix, a feature request, or
  another change, must be a merge request and another person must review it.
* The language is English, in the documentation, for pull requests, issues
  and also commit messages.
* Each role is listed in the README.
* Each role must have a meta information file (``$ROLE/meta/main.yml``).
* We use multiple features, like `issue-tracker`_, `pull-request`_, `labels`_
  for requests and issues.
* The `continuous integration`_ must pass.


DEVELOPEMENT ENVIRONMENT
========================
To setup the development environment you should clone the repository
`ansible-guide`_.

.. code-block:: Bash

  git clone https://github.com/adfinis-sygroup/ansible-guide.git
  cd ansible-guide
  git submodule update --init

There is a vagrant box for each supported distribution. ``vagrant up`` will
start all boxes one by one and will automatically provision those with
Ansible. To restart a provisioning task, you can use
``vagrant provision <distribution>``.


CONTINUOUS INTEGRATION
======================
The continuous integration (CI) will do some checks, like

* yaml syntax check
* Ansible syntax check
* Ansible linting (for best current practice and some additional checks)


LICENSE
=======
GNU GENERAL PUBLIC LICENSE Version 3

See the `LICENSE`_ file.


.. _ansible-guide: https://github.com/adfinis-sygroup/ansible-guide.git
.. _ansible-roles: https://github.com/adfinis-sygroup/ansible-roles.git
.. _issue-tracker: https://github.com/adfinis-sygroup/ansible-roles/issues
.. _pull-request: https://github.com/adfinis-sygroup/ansible-roles/pulls
.. _labels: https://github.com/adfinis-sygroup/ansible-roles/issues/labels
.. _continuous integration: https://travis-ci.org/adfinis-sygroup/ansible-roles
.. _LICENSE: LICENSE


.. vim: set ft=rst sw=2 ts=2 et wrap tw=80 :
