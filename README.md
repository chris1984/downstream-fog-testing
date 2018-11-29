# Fog-testing

Ansible role to do regression testing of fog-vsphere against Red Hat Satellite on oVirt

## Build status

[![Build Status](https://travis-ci.org/chris1984/downstream-fog-testing.svg?branch=master)](https://travis-ci.org/chris1984/downstream-fog-testing)

## Requirements

* Python >= 2.6
* ovirt-engine-sdk-python >= 4.2.4
* Ansible 2.7

## Role Variables

* Variables are all in defaults/main.yml

```yaml
---
cp_id: Compute Profile ID
cr_id: Compute Resource ID
fog_version: Fog version that you are testing with on Red Hat Satellite
fogpatch_url: URL to GitHub Patch to download and test
hammer_password: Password for hammer
hammer_user: Username for hammer
hammer_version: Version of hammer on the Satellite
hostgroup_id: Hostgroup ID
location_id: Location ID
medium_id: Installation medium ID
org_id: Organization ID
os_id: Operating system ID
ptable_id: Partition Table ID
revert_vm: Put true if you want to revert the VM snapshot after testing
rhv_ca: Path to the RHV CA
rhv_cluster: Cluster name in RHV
rhv_password: Password for RHV
rhv_snapshotid: Snapshot ID for VM
rhv_url: URL to RHV 
rhv_username: Username for RHV
sat_domain: Domain setup in Satellite to append to short name host during creation
test_pr: Put true if running in PR test mode.
update_satellite: Put true if you want to perform a yum update * and then an installer run with the --upgrade flag
vm_timeout: 567 # Configurable timeout for waiting before starting more VM creation tasks
```

## Example Playbook

```yaml
---
- name: Start fog-vsphere Red Hat Satellite regression testing
  hosts: all
  become: true
  remote_user: root
  become_method: enable
  gather_facts: no
  serial: 1

  roles:
    - chris1984.downstream_fog_testing
```

### License

MIT

### Author Information

* Chris Roberts - chrobert@redhat.com  - https://www.linkedin.com/in/croberts84/
* Work at Redhat on the Foreman/Katello projects and also maintain fog-vsphere.