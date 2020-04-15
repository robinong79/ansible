# Ansible
Repository for different Ansible playbooks to make life easier

## Prerequisites
- Have a VM/HyperV/Server with CentOS 7 installed
- update yum (sudo yum update)
- install ansible (sudo yum install ansible)
- Check that ansible has installed correctly (ansible --version)

## Notes
The playbooks are build to run localy on the CENTOS server. If you want to run it on different servers than you have to change the connection option in the playbook file to **remote** and setup a correct ssh connection (ssh keys) to your servers.

The playbooks need to be run as sudo

# Playbooks

---

## Docker Install

### Purpose
- Uninstall Docker
- Install the latest Docker version on a CentOS 7 server
- Add current logged in user to Docker group

---




