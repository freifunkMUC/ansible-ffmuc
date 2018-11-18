# ansible-ffmuc

Those ansible playbooks use mitogen to run faster, you need to have it installed and maybe adjust the path in ```ansible.cfg````.

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




