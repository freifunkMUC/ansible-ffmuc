# ansible-ffmuc

Those ansible playbooks use mitogen to run faster, you need to have it installed and maybe adjust the path in `ansible.cfg`.

Those playbooks do nothing else than setting up our jumphost. And initialising new machines with a salt-minion.
## Install mitogen with

     pip install mitogen

## Install dependencies

    ansible-galaxy install -r requirements.yml

## Run Ansible

### Possible Targets

- all
- jumphost
- new

### Testing

     ansible-playbook playbook-default-install.yml --ask-sudo-pass --extra-vars "target=test" --check --diff

### Actual run

    ansible-playbook playbook-default-install.yml --ask-sudo-pass --extra-vars "target=test"

## Debugging

List group membership:

     ansible localhost -m debug -a 'var=groups'

List all variables for a host (dc3):

     ansible dc3 -m debug -a "var=hostvars[inventory_hostname]"

