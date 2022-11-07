# ee-labs
A lab for execution environment training

## Purpose
This lab is intended to help show what makes certain plays and conditions incompatible with running Ansible in Execution Environments

## Lab Environment
The lab environment is self-built. This has been tested with a RHEL 8 desktop environment, but should be applicable to any lab with libvirt available for virtual machines.

## Workflow
Clone the repository to your local machine
The playbook "classic.yml" will work in command line ansible, but not execution environments.
You can verify that by running "ansible-playbook -i localhost classic.yml" and a virtual machine will be created.
This will not run under a default execution environment. This lab is intended to teach you how to update the playbooks and/or execution environments to run this.
