=============
ANSIBLE ROLES
=============

Ansible roles to manage your infrastructure in an automated and reproducable
way.


FEATURES
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
   (``git submodule add git@git.adfinis-sygroup.ch:ad-sy/ansible-roles.src.git
   adsy-roles``)
#. Configure Ansible to use the additional roles path

.. code-block:: Ini

  [defaults]
  ansible_managed     = Warning: File is managed by Ansible [https://git.adfinis-sygroup.ch/ad-sy/ansible-roles.src]
  retry_files_enabled = False
  hostfile            = ./hosts
  roles_path          = ./adsy-roles

4. Create your own project specific roles in directory ``roles``, ansible will
   use both directories (with precedence of ``roles``).


ROLES
=====
Currently the repository features the following roles:

+---------------+-----------------------------------------------------------+
| Role          | Description                                               |
+===============+===========================================================+
| ansible       | install base packages and ansible related packages        |
+---------------+-----------------------------------------------------------+
| console       | manage adsy standard tooles, bashrc and vimrc             |
+---------------+-----------------------------------------------------------+
| hostname      | set system hostname                                       |
+---------------+-----------------------------------------------------------+
| grub          | install and configure grub                                |
+---------------+-----------------------------------------------------------+
| mariadb       | manage a mariadb server and client (if mariadb is not     |
|               | available, mysql will be installed instead)               |
+---------------+-----------------------------------------------------------+
| network       | manage network interfaces and ip addresses and routes     |
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
| users         | manage posix users and groups                             |
+---------------+-----------------------------------------------------------+


CONTRIBUTIONS
=============
Contributions are more than welcome! Please feel free to open new issues or
pull requests.

We have some contribution rules:

* Each change, regardless if it's a new role, a bugfix, a feature request, or
  another change, must be a merge request and another person must review it.
* The language is english.
* Each role is listed in the README.
* For each role exists a meta information file (``$ROLE/meta/main.yml``).
* We use multiple features, like `issue-tracker`_, `merge-request`_,
  `labels`_ for requests and issues `continuous integration`_.


DEVELOPEMENT ENVIRONMENT
========================
To setup the developement environment you should clone the repository
`ansible-guide.doc`_.

.. code-block:: Bash

  git clone git@git.adfinis-sygroup.ch:ad-sy/ansible-guide.doc.git
  cd ansible-guide.doc
  git submodule update --init

There is a vagrant box for each supported distribution. ``vagrant up`` will
start all boxes one by one and will automatically provision those with
ansible. To restart a provisioning task, you can use
``vagrant provision <distribution>``.


CONTINUOUS INTEGRATION
======================
The continuous integration (CI) will do some checks, like

* yaml syntax check
* ansible syntax check
* ansible linting (for best current practice and some additional checks)


LICENSE
=======
GNU GENERAL PUBLIC LICENSE Version 3

See the `LICENSE`_ file.


.. _ansible-guide.doc: https://git.adfinis-sygroup.ch/ad-sy/ansible-guide.doc
.. _ansible-roles.src: https://git.adfinis-sygroup.ch/ad-sy/ansible-roles.src
.. _issue-tracker: https://git.adfinis-sygroup.ch/ad-sy/ansible-roles.src/issues
.. _merge-request: https://git.adfinis-sygroup.ch/ad-sy/ansible-roles.src/merge_requests
.. _labels: https://git.adfinis-sygroup.ch/ad-sy/ansible-roles.src/labels
.. _continuous integration: https://git.adfinis-sygroup.ch/ad-sy/ansible-roles.src/pipelines
.. _LICENSE: LICENSE


.. vim: set ft=rst sw=2 ts=2 et wrap tw=76:
