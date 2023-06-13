# Roles in AAP

## Introduction

I'm going to explain how to easily get started with Ansible Roles.

I will make a simple role that takes care of installing and configuring Postfix on a RHEL box, and make sure that any e-mail is sent to a next hop that can be defined as a parameter to the role.

## Documentation

https://galaxy.ansible.com/docs/contributing/creating_role.html

## Howto

ansible-galaxy init mxout

tree -d --matchdirs mxout
mxout
├── defaults
├── files
├── handlers
├── meta
├── tasks
├── templates
├── tests
└── vars



