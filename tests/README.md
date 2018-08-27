# Test setup

This is an example setup, based on Vagrant + Virtualbox, that allows to easily run ansible commands to test the module.

# Requirements

- Vagrant > 2.0.0
- Virtualbox

# Setup

In `$WORK_DIR/roles/redirectionio.agent/tests`:

- provision VM: `vagrant up`
- connect to the VM to check the configuration: `vagrant ssh`
- destroy VM when needed: `vagrant destroy -f`

In `$WORK_DIR`, launch the provisionning:

- run ansible-playbook: `ansible-playbook roles/redirectionio.agent/tests/test_redirectionio_full.yml -i roles/redirectionio.agent/tests/inventory`
