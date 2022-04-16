# Ansible for deploying Gitbucket application and using apache2 as a LoadBalancer
Playbook create database with needed privileges for our application, set up the NFS server for application data, create a loadbalancer using apache2 with needed configuration files, installing tomcat, and deploy our application to app servers.

For specify variables when we run our ansible playbook we need to use option __-e (--extra-vars)__
```
 ansible-playbook example.yml –extra-vars “group=production”
```
You can specify as extra vars
 - IP of NFS, DB, LB, App servers:
     - server_app_1: 192.168.33.25
     - server_app_2: 192.168.33.55
     - server_db: 192.168.33.35
     - server_nfs: 192.168.33.45

 
 - IP for giving access to DB (specify this ip without fourth octet):
      - ip_for_access_db: 192.168.33
  
      _P.S. we need it to do like 192.168.33.0/24 in script .sql for giving privileges. It can be use only for network with /24 mask. If we need other mask we need to change template .sql script. Example of 172.16.0.0/16 --> 172.16.%.%_

 - Gitbucket home directory:
    
     - gitbucket_home_dir: /mnt/gitbucket_home
    
 - Tomcat version (Good practice is to use stable version): 
    
      - tomcat_version: 9.0.56
     
 - NFS ip network and mask:
      - ip_network: 10.26.0.0
      - mask_network: 22
