# ansible-ffmuc

Those ansible playbooks use mitogen to run faster, you need to have it installed and maybe adjust the path in `ansible.cfg`.

## Install mitogen with

     pip install mitogen

## Run Ansible

### Possible Targets

- all
- test
- gateways
- proxmox
- jumphost

### Testing

     ansible-playbook playbook-default-install.yml --ask-sudo-pass --extra-vars "target=test" --check --diff

### Actual run

    ansible-playbook playbook-default-install.yml --ask-sudo-pass --extra-vars "target=test"

## Debugging

List group membership:

     ansible localhost -m debug -a 'var=groups'

List all variables for a host (dc3):

     ansible dc3 -m debug -a "var=hostvars[inventory_hostname]"

## Proxmox handling

All code to handle Proxmox is based on the work of Musee Ullah (https://github.com/lae). 
The original code can be found here: https://github.com/lae/ansible-role-proxmox/tree/develop
