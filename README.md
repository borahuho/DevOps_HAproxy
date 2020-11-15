# DevOps_HAproxy

This vagrant will install 3 Ubuntu 18.04 machines, 2x webserver, 1x HAproxy server.
It will add some default users, groups and directory's.
This Vagrant is to practice with Loadbalancing and security.
This repository is intended for educational purpose only.


## Prerequisites

Works on Windows 10 and tested on macOS (macOS needs the Virtualbox extension pack).

Software needed:
* Virtualbox 5.0 or higher
* Git bash for Windows
* Vagrant 2.2.6 or higher


## Demo installation && use Vagrant

Youtube: https://youtu.be/KABnIuaA8SM


## Demo loadbalancing with HAproxy

Youtube:  https://youtu.be/YLlT9LXN5HQ


## Installation

* Install Virtualbox: https://www.virtualbox.org/wiki/Downloads
* Install Git bash for Windows: https://gitforwindows.org/
* Install Vagrant for Windows: https://www.vagrantup.com/downloads.html

## Run this Vagrant VM
Open **Git Bash** in Windows
```
cd Documents
mkdir vagrant && cd vagrant
git clone https://github.com/borahuho/DevOps_HAproxy
cd DevOps_HAproxy
vagrant up
```
## Mission

Read your mission in "Opdracht"

## Network
Vagrant VM will be set up with 2 network adapters
```
Nat : DHCP
Localhost (web1): 192.168.10.251

Nat : DHCP
Localhost (web2): 192.168.10.252

Nat : DHCP
Localhost (proxy): 192.168.10.254

```
## Vagrant commands
Start VM's with Vagrant
```
vagrant up
```
Pause a VM
```
vagrant suspend
```
Restart a paused VM
```
vagrant resume
```
Stop and shutdown a VM
```
vagrant halt
```
Remove a VM
```
vagrant destroy
```
ssh in to the VM
```
vagrant ssh web01
vagrant ssh web02
vagrant ssh proxy
```

