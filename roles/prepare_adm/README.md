prepare_adm
===========

Basic description for prepare_adm

Requirements
------------

Ansible 2.8 or higher

Red Hat Enterprise Linux 7 or equivalent

Valid Red Hat Subscriptions

Role Variables
--------------

Currently the following variables are supported:

### General

* `prepare_adm_become` - Default: true. If this role needs administrator
  privileges, then use the Ansible become functionality (based off sudo).
* `prepare_adm_become_user` - Default: root. If the role uses the become
  functionality for privilege escalation, then this is the name of the target
  user to change to.

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: prepare_adm-servers
  roles:
    - role: oasis_roles.system.prepare_adm
```

License
-------

GPLv3

Author Information
------------------

Author Name <authoremail@domain.net>
