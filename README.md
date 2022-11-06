# Ansible Collection - community.cnv

This collection contains:
1. Playbooks
1. Roles
1. Supporting files/scripts

Used to provision Virtual Machines on OpenShift Clusters.

Documentation for each role and playbook can be found in their respective subdirectories.

* [roles/vm/README.md](roles/vm/README.md)
* [playbooks/README.md](playbooks/README.md)

** Technical Preview - Still Under Development **
To cleanup a VM you can run the `cleanup_vm.sh` script located in `~/.ansible/collections/ansible_collections/community/cnv/supporting_files/cleanup_vm.sh`
It takes the short hostname of the VM(s) as an argument. IE `cleanup_vm.sh virtualmachine1 virtualmachine2`
