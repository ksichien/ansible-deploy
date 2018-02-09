# ansible-playbooks
This is a small collection of Ansible playbooks I've written to automate the installation, configuration and maintenance of several Debian GNU/Linux servers.

There are several roles included:
- common: create user accounts and configure ssh access
- firewall: configure iptables and fail2ban
- dns: configure dns using bind
- web: configure a ruby on rails web application using postgresql, nginx and passenger

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
