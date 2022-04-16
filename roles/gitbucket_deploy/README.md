Gitbucket deploy
=========

This role is using to deploy gitbucket application to app servers.

Requirements
------------

We need to install one additional plugin for mounting our NFS server to application instance.
```
ansible-galaxy collection install ansible.posix
```

Role Variables
--------------
We need to specify these variables
```
server_db: "10.26.0.217"
server_nfs: "10.26.0.214"
gitbucket_home_dir: /mnt/gitbucket_home
tomcat_version: 9.0.56
```
There are IP's of our NFS and DB servers, application home directory for storing appdata and the version of tomcat that we using.

Dependencies
----------------
First of all we need to install tomcat in our app servers so we using another role __tomcat_setup__ that is stored in our repository too.

Example Playbook
----------------
We need to set up first tomcat than deploy application, so we use these roles together.
```
  - name: Setup tomcat and deploy application
    hosts: app_servers
    become: yes

    roles:
      - tomcat_setup
      - gitbucket_deploy
```
