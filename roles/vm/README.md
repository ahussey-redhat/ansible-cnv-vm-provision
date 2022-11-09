VM
=========

This role deploys a development virtual machine to a specified CNV OpenShift cluster

Requirements
------------
```yaml
collections:
  - name: kubernetes.core
  - name: community.general
```

Role Variables
--------------

| Variable | Default | Required | Description |
| --- | --- | --- | --- |
| vm_ssh_pubkey | lookup ~/.ssh/id_rsa.pub | yes | User's SSH public key to be injected into virtual machine image |
| vm_domain | example.com | yes | Virtual Machine's domain |
| vm_project | N/A | yes | OpenShift project/namespace to deploy the VM |
| vm_satellite_capsule | N/A | no | Satellite capsule for the VMs |
| vm_root_password | password | yes | Initial root password |
| vm_update_dns | false | yes | Whether to interact with Infoblox to add/modify host records |
| vm_spec | N/A | no | a virtual machine specification hash |

vm_spec example
```yaml
vm_spec:
  name: test-vm
#  activation_key: rhel8-prod # Only required if registering to Satellite
  image: https://download.fedoraproject.org/pub/fedora/linux/releases/36/Cloud/x86_64/images/Fedora-Cloud-base-36-1.5.x86_64.qcow2
  memory: 4096
  cpu: 4
  disk_size: 25 # default 20, measured in Gibibytes
  primary_ip: "10.0.0.10"
  networks:
    - type: bridge
      source_vlan: 10
```

Dependencies
------------
```yaml
roles:
  - name: rhel-system-roles.network # or linux-system-roles.network
collections:
  - name: kubernetes.core
  - name: community.general
```

Example Playbook
----------------

```yaml
---
- name: Deploy the VM(s)
  import_playbook: community.cnv.vm_deploy

- name: Ensure the VM(s) are available
  hosts: all
  gather_facts: no
  remote_user: root
  tasks:
    - name: Ensure VM(s) are online
      ansible.builtin.wait_for_connection:
        timeout: 600
        sleep: 10
```

License
-------

BSD
