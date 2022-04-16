Role Name
=========

This role is using for configuration our MariaDB server

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Specify this ip without fourth octet
```
ip_for_access_db: 192.168.33
```

P.S. we need it to do like 192.168.33.0/24 in script .sql for giving privileges. It can be use only for network with /24 mask. If we need other mask we need to change template .sql script. Example of 172.16.0.0/16 --> 172.16.%.%
Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

