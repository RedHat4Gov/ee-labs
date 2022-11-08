# ee-labs
A lab for execution environment training

## Purpose
This lab is intended to help show what makes certain plays and conditions incompatible with running Ansible in Execution Environments.

## Lab Environment
The lab environment is self-built. This has been tested with a RHEL 8 desktop environment, but should be applicable to any lab with libvirt available for virtual machines.  This currently assumes that the default network for virtual machines is 192.168.122.0/24 and has been hardcoded as such.

### Setup
Assuming a RHEL 8 machine
1. Install virtualization and viewer
`sudo dnf install virt-viewer`
2. Ensure virtualization has been started and the default network is available. This can be verified with
`sudo virsh net-list`
3. Install Ansible-navigator. This package, for RHEL 8, is in  the repository `ansible-automation-platform-2.2-for-rhel-8-x86_64-rpms`
4. Download the latest RHEL 8 iso and place it in "{{ iso_path }}", by default this is `/var/lib/libvirt/images`

## Workflow
Clone the repository to your local machine

Copy the vars/main.yml and create a new vars file named "{{ server_name }}.yml", where server_name is the FQDN of the server intended to be built.

In the directory you cloned to (/path/ee-labs), you can run the command
`ansible-playbook -i localhost tasks/main.yml -e "server_name=demo.example.local"

This should create a virtual machine and create an entry in /etc/hosts.

## Lab

This playbook will not run under a default execution environment. This lab is intended to teach you how to update the playbooks and/or execution environments to run this.

### Guidance