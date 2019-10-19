Ansible Role: Docker and Docker Compose setup
=========

**Install and Setup Docker and Docker Compose on any CentOS/RedHat Linux system.**

This Ansible role will perform all necessary tasks to setup and run Docker and Docker Compose:

  * Install packages necessary for YUM
  * Add and setup official Docker YUM repositories.
  * Add user to Docker group.
  * Start de Docker Daemon and enables it at start up
  
This role was created as part of [containerized-wordpress-project](https://github.com/AdnanHodzic/containerized-wordpress-project)

Requirements
------------

None.

Role Variables
--------------

If you want to change the user which will be added to Docker group
uncomment and change contents of `system_user` variable (see: `defaults/main.yml`)

```
system_user: docker
```

Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: servers
  remote_user: "{{ system_user }}"
  gather_facts: yes
  become: yes

  roles:
    - { role: ansible-role-centos-docker-compose }
```

License
-------

GPLv3
