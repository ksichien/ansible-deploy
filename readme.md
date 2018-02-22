# Ansible Playbooks
This is a collection of Ansible playbooks I've written to automate the installation, configuration and maintenance of several Debian GNU/Linux servers.

## Overview

There are several roles included:
- common: create user accounts and configure ssh access
- dns: configure dns using bind
- firewall: configure the firewall using ufw and fail2ban
- media: configure file sharing using samba
- monitoring: configure zabbix agent
- web: configure multiple web applications using nginx and passenger

A lot of settings can be changed in the roles' respective `defaults` and `vars` folders.

The hosts file in this project has also been set up to work with an ssh bastion for all offsite hosts.
An `~/.ssh/config` example file has been included for reference.

Finally, a Vagrantfile and a vagrant.yml playbook have also been included for testing everything out.

## Usage

In order to do use them, the following process needs to be followed:
- Install Virtualbox, Vagrant & Ansible
```
$ sudo apt install virtualbox vagrant ansible
```
- Install the vbguest plugin for Vagrant
```
$ vagrant plugin install vagrant-vbguest
```
- Start the Vagrant virtual machine, this may take some time
```
$ vagrant up
```
- Execute the vagrant.yml playbook with Ansible on the Vagrant machine
```
$ vagrant provision
```
- Destroy the Vagrant machine when finished
```
$ vagrant destroy
```
