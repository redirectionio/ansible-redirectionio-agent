# Ansible redirectionio-agent role

This role installs the [redirection.io](https://redirection.io/) agent. It supports Debian and RHEL-based Linux distributions.

## Installation

Simply run the following command:

```
ansible-galaxy install redirectionio.agent
```

## Role vars

 * `redirectionio_token`: your redirection.io project token
 * `redirectionio_instance_name`: the name of this instance, in order to track it in the web interface

## Example playbook

```yml
- hosts: webservers
  roles:
    - { role: redirectionio.agent, become: true }
  vars:
    redirectionio_token: 'abcdefgh-ijkl-mnop-qrst-uvwxyz123456'
    redirectionio_instance_name: 'The magical frontend #1'
```

## Dependencies

This role has no dependency.

## License

This role is available under the terms of the MIT License.
