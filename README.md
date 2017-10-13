Ansible Role for RabbitMQ
=========

This an ansible role for RedHat and Debian Family

Requirements
------------
RedHat and Ubuntu and the basic package erlang.
Erlang key for debian: http://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc
Erlang key for RedHat: https://www.rabbitmq.com/rabbitmq-signing-key-public.asc

==Epel Repo should be installed in RedHat: package name={{ epel-release}}

Role Variables
--------------
```Yaml
rbadmin: admin
rbpassword: password
This is the variable rabbitmq user and password
```

Dependencies
------------

The dependency is erlang and scot and rabbitmq-server

RabbitMQ package for RedHat: https://www.rabbitmq.com/releases/

rabbitmq-server/v3.6.1/rabbitmq-server-3.6.1-1.noarch.rpm

Erlang package for Debian: https://packages.erlang-solutions.com/

Erlang-solutions_1.0_all.deb

Erlang package for RedHat: http://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      roles:
         - { role: rabbitmq }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
