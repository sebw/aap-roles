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

When you are happy with your role, you can start using it in a playbook.

```yaml
  tasks:
  - name: call mxout role
    ansible.builtin.include_role:
      name: mxout
```

Variables can be specified in multiple locations (AAP, defaults folder of the role, vars in the playbook, on a host variable, on a group variable, etc.). There are 22 ways to declare variables, be smart and keep things simple!

## Ansible development workflows

There are many possible workflows and it is possible to use multiple tools to develop Ansible content (ansible-navigator, ansible-playbook, AWX, AAP, etc.).

One possibility is to write your code, commit your changes to a Git repository and testing your changes directly in Ansible Automation Platform against a test inventory.
