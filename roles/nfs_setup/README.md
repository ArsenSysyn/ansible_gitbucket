NFS setup
=========

This role is using to set up the NFS server for storing appdata between multiple applicaton servers.

Requirements
------------

Any additional requirements.

Role Variables
--------------
We need to specify these variables
```
ip_network: 10.26.0.0
mask_network: 22
```
These variables are using to give the permission for network with IP address and mask to use NFS server.

Example Playbook
----------------

How to use our role
```
- name: Setup NFS server
    hosts: nfs
    become: yes

    roles:
      - nfs_setup
```