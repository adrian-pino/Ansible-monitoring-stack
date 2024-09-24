# Ansible

This repository was created using Ansible version 2.13.3. It has been validated with 2.16.10. If having problem launching playbooks, please make sure you have a high enough version of Ansible.

## Architecture

This repository is composed of multiple folders, used as follows:

```.
├── README.md              -> this file
├── inventories            -> hosts inventory files
│  └── hosts.yml           -> describes the different hosts
├── playbooks              -> ansible playbooks
├── roles                  -> ansible roles
```

## Using ansible

To use ansible, you must first install ansible. Follow the steps described [here](https://docs.ansible.com/ansible/latest/installation_guide/index.html), depending on your OS.

## How to run it
```.
ansible-playbook -i inventories/hosts.yml playbooks/monitoring.yml -t observer --become --ask-become-pass
ansible-playbook -i inventories/hosts.yml playbooks/monitoring.yml -t target --become --ask-become-pass
```