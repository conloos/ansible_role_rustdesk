# Ansible role for building and running rustdesk.
=================================================

**summary**
This role is for building and running rustdesk. 
Look in the tasks directory for each configuration.
All configurations are held atomically via their own files.

## Necessary preparations
A docker runtime environment must exist on the system.
Or use: https://github.com/conloos/ansible-docker

## Variables that have to be defined

| variable | description | mandantory |
| -------- | ----------- | ---------- |
| rustdesk.hbbs_data_dir | Path to store persistent hbbs data | False |
| rustdesk.server_version_tag | docker Version Tag | False |
| rustdesk_public_address | docker Version Tag | True |
| rustdesk_recreate_container_and_keys | recreate the container and keys | False |

# example playbook
```
---
- hosts: 
    - example.com
  become: True
  vars:
    rustdesk_public_address: example.com
  vars_files:
    - group_vars/vault.yml
  tasks:
  roles:
    - rustdesk
```
