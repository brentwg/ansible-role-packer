# Ansible Role - Packer
[![Build Status](https://travis-ci.org/brentwg/ansible-role-packer.svg?branch=master)](https://travis-ci.org/brentwg/ansible-role-packer)

This role installs Hashicorp's [Packer](https://www.packer.io) application.  

This is based on Jeff Geerling's [Ansible Role: Packer](https://github.com/geerlingguy/ansible-role-packer). However, I've slightly modified it to preserve previous downloaded versions and I've added a symlink so that you can switch between versions - depending on which one is specified in this role.  

## Requirements

None.

## Role Variables
User modifiable variables and defaults are listed below. (For all variables, see `defaults/main.yml`):

```
packer_version: "1.2.0"
```  
The version of Packer to install.  

```
packer_arch: "amd64"
```  
The system architecture that you are using (eg. `386` or `amd64`).

The installation path is:  
```
/usr/local/packer-{{ packer_version }}/packer
```  

And the symlink to the specified version is created here:  
```
/usr/local/bin/packer
```

## Dependencies

None.

## Sample Playbook

```
- hosts: all

  vars:
    packer_version: "1.2.0"
    packer_arch: "amd64"

  roles:
    - brentwg.packer
```  