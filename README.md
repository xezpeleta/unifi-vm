unifi-vm
========

This project will help you deploying UniFi controller in a VirtualBox VM.

## Required
 - VirtualBox 4.3 or greater
 - Vagrant 1.6 or greater
 - Ansible 1.7 or greater

## Instructions

Start and provision the vagrant environment:
```sh
cd unifi-vm
vagrant up
```

Vagrant will create a Debian VM and it will provision it with the last UniFi controller stable version.

## Use

Thanks to Vagrant configurations, **8080** and **8443** ports are forwarded to localhost. You can access to web GUI using the address in **your host machine**:

```
http://localhost:8080
```
