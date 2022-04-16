LoadBalancer setup
=========

This role is using to set up a LoadBalancer using apache2 as a LoadBalancer.

Requirements
------------

Any additional requirements.

Role Variables
--------------
We need to specify the application servers IP's for adding that to apache2 configuration file.
```
server_app_1: "10.26.0.157"
server_app_2: "10.26.0.177"
```

Dependencies
------------

For using this role first of all we need to have the servers with running applications.

Example Playbook
----------------
How to use our role
```
  - name: Setup Apache Load Balancer
    hosts: lb
    become: yes

    roles:
      - lb_setup
```

