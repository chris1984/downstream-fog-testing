# Fog-testing

Ansible role to do regression testing of fog-vsphere against Foreman on oVirt

## Requirements

* Python >= 2.6
* ovirt-engine-sdk-python >= 4.2.4
* Ansible 2.7

## Role Variables

* Variables are all in role/defaults/main.yml

```yaml
---
hammer_user:
hammer_password:
hostgroup_id:
location_id:
org_id:
cr_id:
cp_id:
ptable_id:
medium_id:
os_id:
image_name:
test_pr:
fog_version:
fogpatch_url:
revert_vm:
update_foreman:
rhv_username:
rhv_password:
rhv_url:
rhv_ca:
rhv_vmname:
rhv_snapshotid:
```

## Example Playbook

```yaml
---
- name: Start fog-vsphere regression testing
  hosts: all
  become: true
  remote_user: root

  roles:
    - chris1984.downstream_fog_testing
```

### License

MIT

### Author Information

* Chris Roberts - chrobert@redhat.com  - https://www.linkedin.com/in/croberts84/
* Work at Redhat on the Foreman/Katello projects and also maintain fog-vsphere.