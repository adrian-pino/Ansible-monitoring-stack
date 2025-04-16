# Deploying a docker-based monitoring stack using Ansible
Reference: https://cloud.theodo.com/en/blog/prometheus-monitoring-ansible

## Ansible

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

## Requirements
Ensure the following dependencies are installed:

- **Ansible**: Install Ansible on your local machine or a remote server, ensuring that target devices are accessible. Refer to the official installation guide [here](https://docs.ansible.com/ansible/latest/installation_guide/index.html) for setup instructions.

- **Docker**: Docker must be installed on each node to be monitored. Follow the installation steps provided [here](https://docs.docker.com/engine/install).

## How to run it
```.
ansible-playbook -i inventories/hosts.yml playbooks/monitoring.yml -t observer --become --ask-become-pass
ansible-playbook -i inventories/hosts.yml playbooks/monitoring.yml -t target --become --ask-become-pass
```
