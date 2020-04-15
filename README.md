# Ansible
Repository for different Ansible playbooks to make life easier

## Prerequisites
- Have a VM/HyperV/Server with :
    - CentOS 7 or
    - Debian or
    - Fedora or
    - Ubuntu
- update yum (sudo yum update)
- install ansible (sudo yum install ansible) (Minimal version of Ansible is 2.4)
- Check that ansible has installed correctly (ansible --version)

### Debian (Stretch 9)
- Install dirmngr (to get latest release of Ansible)
    - $ sudo apt-get install dirmngr --install-recommends
- Add the Ansible resource to /etc/apt/sources.list
    - deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main
- Update apt
    - $ sudo apt update    
- Install ansible
    - $ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
    - $ sudo apt update
    - $ sudo apt install -y ansible
- Make sure you are on a verson higher than 2.4
    - $ ansible --version

### Ubuntu (Bionic 18.04)
- $ sudo apt update
- $ sudo apt install software-properties-common
- $ sudo apt-add-repository --yes --update ppa:ansible/ansible
- $ sudo apt -y nstall ansible

### Fedora (30)
- $ sudo dnf update (This might take a while)
- $ sudo dnf install ansible


## Notes
- The playbooks are build to run localy on a server. If you want to run it on different servers than you have to change the connection option in the playbook file to **remote** and setup a correct ssh connection (ssh keys) to your servers.

- The playbooks need to be run as sudo

- You might need more modules installed per OS. Ansible should show this in the stdout or stderror

- The Reboot on Fedora will not work with Ansible on localhost. Use a controller instead when needed

# Playbooks

---

## Docker Install

### Purpose
- Uninstall Docker
- Install the latest Docker version on:
    - CentOs (7) (Verified on HyperV with CentOs 7)
    - Debian (Verified on AWS EC2 Debian Stretch 9.0 )
    - Fedora (Verified on AWS EC2 Fedora 30.0 / Reboot doesnt work when executed on Local server itself )
    - Ubuntu (Verified on AWS EC2 Ubuntu Bionic 18.04)
- Add current logged in user to Docker group

---

# Usage

## Git repo
- Create a directory where you want the Ansible playbooks to run from
- Go to this directory and clone the repo from https://github.com/robinong79/ansible.git
- Move to /ansible/playbooks/docker_install/
- Run the Ansible command to install Docker
    - $ sudo ansible-playbook -i hosts install_docker.yml
- Wait for the playbook to end.
- Congratz. You have docker installed on your OS

# Handy Ansible Commands
- ansible localhost -m setup | grep distribution




