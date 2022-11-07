# ee-labs
A lab for execution environment training

## Purpose
This lab is intended to help show what makes certain plays and conditions incompatible with running Ansible in Execution Environments.

## Lab Environment
The lab environment is self-built. This has been tested with a RHEL 8 desktop environment, but should be applicable to any lab with libvirt available for virtual machines.  This currently assumes that the default network for virtual machines is 192.168.122.0/24 and has been hardcoded as such.

## Workflow
Clone the repository to your local machine

Copy the vars/main.yml and create a new vars file named "{{ server_name }}.yml", where server_name is the FQDN of the server intended to be built.

In the directory you cloned to (/path/ee-labs), you can run the command
`ansible-playbook -i localhost tasks/main.yml -e "server_name=demo.example.local"

This should create a virtual machine and create an entry in /etc/hosts.

## Lab

This playbook will not run under a default execution environment. This lab is intended to teach you how to update the playbooks and/or execution environments to run this.