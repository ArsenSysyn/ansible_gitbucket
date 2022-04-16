Role Name
=========

This role is using for configuration our MariaDB server

Requirements
------------
We need to install a community.mysql plugin for creating our database and for using our .sql scripts which are created from the templates.
```
ansible-galaxy collection install community.mysql
```
Role Variables
--------------

Specify this ip without fourth octet
```
ip_for_access_db: 192.168.33
```

P.S. we need it to do like 192.168.33.0/24 in script .sql for giving privileges. It can be use only for network with /24 mask. If we need other mask we need to change template .sql script. Example of 172.16.0.0/16 --> 172.16.%.%


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: Setup DB server
    hosts: db
    become: yes

    roles:
      - db_setup

