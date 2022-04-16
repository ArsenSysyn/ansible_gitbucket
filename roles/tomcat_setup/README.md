Tomcat setup
=========

This role is using to install tomcat to the application servers.

Requirements
------------

Any additional requirements.

Role Variables
--------------
We need to specify only one variable - tomcat version.
```
tomcat_version: 9.0.56
```
Example Playbook
----------------
How to use our role
```
  - name: Setup tomcat
    hosts: app_servers
    become: yes

    roles:
      - tomcat_setup
```