ceph_inventory
===========

Generates an inventory file for Ceph Ansible to run, based on the current
inventory of hosts attached to the system.

Requirements
------------

Ansible 2.8 or higher

Red Hat Enterprise Linux 7 or equivalent

Valid Red Hat Subscriptions

Role Variables
--------------

Currently the following variables are supported:

### General

* `ceph_inventory_adm_group` - Default: adm. The name of the current inventory
  group containing the admin host.
* `ceph_inventory_mgrs_group` - Default: mgrs. The name of the current inventory
  group containing the Ceph mgrs.
* `ceph_inventory_mons_group` - Default: mons. The name of the current inventory
  group containing the Ceph monitors.
* `ceph_inventory_osds_group` - Default: osds. The name of the current inventory
  group containing the OSD nodes.
* `ceph_inventory_rgws_group` - Default: rgws. The name of the current inventory
  group containing the Rados Gateway nodes.
* `ceph_inventory_grafana_group` - Default: `"{{ ceph_inventory_adm_group }}"`.
  The name of th current inventory group containing the Graphana nodes.
* `ceph_inventory_vars` - Default:
```yaml
  ansible_ssh_extra_vars: '-o StrictHostKeyChecking=no'
```
  A dictionary of key/value pairs that should be set as host inventory vars for
  all of the nodes in the Ceph inventory file.
* `ceph_inventory_destination` - Default: /etc/ansible/hosts. The destination file
  where the inventory should be uploaded to.
* `ceph_inventory_owner` - Default: root. The system user that should have ownership
  of the Ceph inventory file.
* `ceph_inventory_group` - Default: `"{{ ceph_inventory_owner }}"`. The name of the
  system user that should own the inventory file.
* `ceph_inventory_become` - Default: true. If this role needs administrator
  privileges, then use the Ansible become functionality (based off sudo).
* `ceph_inventory_become_user` - Default: root. If the role uses the become
  functionality for privilege escalation, then this is the name of the target
  user to change to.

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: ceph_inventory-servers
  roles:
    - role: oasis_roles.system.ceph_inventory
```

License
-------

GPLv3

Author Information
------------------

Greg Hellings <greg.hellings@gmail.com>
