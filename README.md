# Roles in AAP

## Introduction

I'm going to explain how to easily get started with Ansible Roles.

I will make a simple role that takes care of installing and configuring Postfix on a RHEL box, and make sure that any e-mail is sent to a next hop that can be defined as a parameter to the role.

## Documentation

https://galaxy.ansible.com/docs/contributing/creating_role.html

## Howto

Create the directory structure for a role:

`ansible-galaxy init mxout`

```bash
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
```

Explore the role structure, the `defaults` folder contain default variables that can be overriden at any time.

The `templates` folder contains configuration templates. Some variables require to gather the machine facts with `gather_facts: true` in the playbook calling the role.

The `tasks` folder contains the playbook calling the roles. Variables can be defined there, but we ultimately override variables with extra variables in Ansible Automation Platform.


