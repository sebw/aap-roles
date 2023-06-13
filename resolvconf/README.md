resolvconf
=========

This role configures the /etc/resolv.conf file on a RHEL machine.

Requirements
------------

The resolv.conf file should NOT be managed by NetworkManager.

Role Variables
--------------

Search domain and resolvers can be specified as variables. Default values are provided. At least one resolver is needed.

```
searchdomain: example.org
resolver1: 1.1.1.1
resolver2: 1.0.0.1
```

Author Information
------------------

ansible@example.org
