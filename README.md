# Local Aux Vagrant VM

When mocking the deployment of a server, or cluster. Sometimes is necessary to mock other services like NFS or LDAP.

This repository contains several folders, explained as follow.

- inventory
  - group_vars
    - all
      - _ldap.yml_: LDAP server variables, use this file to re-define them.
      - _nfs.yml_: NFS server variables, use this file to re-define them.


- playbooks
  - all_hosts
    - _generate-hosts-file.yml_: Call role to write _/etc/hosts_ file.

  - support_server
    - _deploy-ldap.yml_: Deploy LDAP service
    - _deploy-nfs.yml_: Deploy NFS service
    - _deploy-support-server.yml_: Deploy All services in this repository


- roles
  - hosts-file: Role to generate _/etc/hosts_
  - ldap: LDAP service role
  - nfs: NFS service role


- scripts
  - all_hosts
    - _ansible_ping.sh_: Ping all hosts in inventory.
    - _generate-hosts-file.sh_: Create _/etc/hosts_

  - support_server
    - _deploy-ldap.sh_:
    - _deploy-nfs.sh_:
    - _deploy-support-server.sh_:


  - ansible.cfg: Ansible configuration file.
  - _init.sh_: Get the **INVENTORY**, point at the **playbooks** and **roles** folders
