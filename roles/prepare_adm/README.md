prepare_adm
===========

Prepares an admin node to run Ceph's own Ansible playbooks from

Requirements
------------

Ansible 2.8 or higher

Red Hat Enterprise Linux 7 or equivalent

Valid Red Hat Subscriptions

Role Variables
--------------

Currently the following variables are supported:

### General

* `prepare_adm_group_vars_dir` - Default none. A list of the
  directories where group vars files should be uploaded FROM. Any name collisions
  inside of multiple entries will clobber one another.
* `prepare_adm_inventory_file` - Default: none. The inventory file, if any,
  that should be uploaded to the remote host.
* `prepare_adm_group_vars_template` - Default: false. Whether files in the
  group\_vars directory, above, should be processed with the `template`
  processor on the current node. If false (the default), they will simply be
  copied.
* `prepare_adm_destination` - Default: /etc/ansible. The destination where
  inventories, group vars, etc should be uploaded to.

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
