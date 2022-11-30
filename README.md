# Ansible Collection - community.cnv

[![Contribute](https://www.eclipse.org/che/contribute.svg)](https://devspaces.apps.sandbox-m2.ll9k.p1.openshiftapps.com#https://github.com/ahussey-redhat/ansible-cnv-vm-provision?che-editor=che-incubator/che-code/insiders)

**Used to provision Virtual Machines on OpenShift Clusters.**

Documentation for each role and playbook can be found in their respective subdirectories.

* [role: vm](roles/vm/README.md)

** Technical Preview - Still Under Development **

(This still needs to be created. Possibly as a module of the collection rather than a random script)

To cleanup a VM you can run the `cleanup_vm.sh` script located in `~/.ansible/collections/ansible_collections/community/cnv/supporting_files/cleanup_vm.sh`
It takes the short hostname of the VM(s) as an argument. IE `cleanup_vm.sh virtualmachine1 virtualmachine2`

## Contributing

[Contributing Guide](CONTRIBUTING.md)

## Collection Maintenance

[Maintainer's Guide](https://docs.ansible.com/ansible/devel/community/maintainers.html)

[Commiter's Guidelines](https://docs.ansible.com/ansible/devel/community/committer_guidelines.html)
