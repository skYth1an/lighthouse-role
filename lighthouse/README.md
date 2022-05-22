Role Name
=========

Lighthouse

Requirements
------------
Firstly install Nginx 
Example
````yaml
    - name: Install Nginx/Git/Update repo
      become: true
      yum:
        name:
          - epel-release
          - nginx
          - git
        state: latest
        update_cache: yes
    - name: Copy nginx conf
      become: true
      template:
          src: templates/nginx.conf.j2
          dest: /etc/nginx/nginx.conf

````

Role Variables
--------------
Variables in catalog defaults/vars  
1. clickhouse_version  
2. clickhouse_packages


Dependencies
------------
For this role need clickhouse

````yaml
 - src: git@github.com:AlexeySetevoi/ansible-clickhouse.git
````



Example Playbook
----------------
````yaml
- name: install Lighthouse
  hosts: lighthouse
  roles:
    - lighthouse
````
License
-------

BSD

Author Information
------------------

Lebedev Igor
