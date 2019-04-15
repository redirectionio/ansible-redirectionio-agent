# Ansible redirectionio-agent role

redirection.io is a Web traffic redirection manager. It provides a collection of tools for website administrators, SEO agencies and developers, which help analyze HTTP errors, setup HTTP redirections and monitor the traffic efficiently.

This role installs the [redirection.io](https://redirection.io/) agent. It supports Debian and RHEL-based Linux distributions.

## Installation

Simply run the following command:

```
ansible-galaxy install redirectionio.agent
```

## Role vars

 * `redirectionio_agent_instance_name`: the name of this instance, in order to track it in the web interface

You may also configure:

 * `redirectionio_agent_enabled` (default: `true`): shall redirection.io be enabled after the playbook is run?
 * `redirectionio_user` (default `redirectionio`): user running the agent
 * `redirectionio_group` (default `redirectionio`): group of the user running the agent
 * `redirectionio_agent_listen` (default `127.0.0.1:10301`): interface listening. Use `/var/run/redirectionio.sock` or `127.0.0.1:10301`
 * `redirectionio_agent_persist` (default `true`): whether or not to store rules on the disk
 * `redirectionio_agent_datadir` (default `/var/lib/redirectionio`): where to store persisted rules
 * `redirectionio_agent_cache` (default: `true`): use in-memory cache to speed-up agent matching
 * `redirectionio_agent_log` (default: `{}`): log configuration directives - see the [configuration template](./templates/agent.yml.j2) for more details.

## Example playbook

```yml
- hosts: webservers
  roles:
    - { role: redirectionio.agent, become: true }
  vars:
    redirectionio_agent_instance_name: 'The magical frontend #1'
```

## Dependencies

This role has no dependency.

## Tests

The role can be tested using the [test instructions](./tests/README.md).

## License

This role is available under the terms of the MIT License.
