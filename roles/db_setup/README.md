DB setup
=========

This role is using to configure MariaDB server

Requirements
------------
We need to install a community.mysql plugin for creating our database and for using our .sql scripts which are created from the templates.
```
ansible-galaxy collection install community.mysql
```
Role Variables
--------------

We need to specify this ip without fourth octet
```
ip_for_access_db: 192.168.33
```

P.S. we need it to do like 192.168.33.0/24 in script .sql for giving privileges. It can be use only for network with /24 mask. If we need other mask we need to change template .sql script. Example of 172.16.0.0/16 --> 172.16.%.%


Example Playbook
----------------

Example of how use our role, in my example I specify variable in vars file, or it can be also specified in group_vars directory. And one more example it specify variable using __- { role: db_setup, ip_for_access_db: 192.168.33 }__

    - name: Setup DB server
    hosts: db
    become: yes

    roles:
      - db_setup

