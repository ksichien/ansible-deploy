# ansible-deploy
This is a small collection of Ansible playbooks I've written to automate the installation and configuration of a Debian GNU/Linux Ruby on Rails webserver. 

There are several roles included:
- common: create user accounts, configure ssh access and the zabbix agent.
- app: clone the web application with git, configure ruby, configure rails
- db: configure postgresql
- web: configure nginx and passenger
- firewall: configure iptables and fail2ban

I've included a Vagrantfile and vagrant.yml playbook for testing everything out.

In order to do this, the following process needs to be followed:
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
