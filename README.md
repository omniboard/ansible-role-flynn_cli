[![Build Status](https://travis-ci.org/omniboard/ansible-role-flynn_cli.svg?branch=master)](https://travis-ci.org/omniboard/ansible-role-flynn_cli)

# Flynn CLI

This Ansible role installs the [Flynn](https://flynn.io) CLI client.
It also configures the Flynn CLI for specific users to have access to a list of Flynn clusters.

## Role Variables

```yml
# Location to place the Flynn CLI executable.
flynn_cli_executable: /usr/local/bin/flynn

# Access to each of the clusters will be configured for each of these usernames.
# If this is not provided, clusters will not be configured (the default).
flynn_cli_users:
- flynnbackups

# List of Flynn clusters along with access information (provided by Flynn after initialization).
flynn_cli_clusters:
- name:
  tlspin: 1234=
  hostname: flynn0.example.com
  key: abcdefg
```

## Example

```yml
- hosts: all
  roles:
  - role: flynn_cli
    flynn_cli_users:
    - flynnbackups
    flynn_cli_clusters:
    - name:
      tlspin: 1234=
      hostname: flynn0.example.com
      key: abcdefg
```

## Dependencies

None

## License

BSD

## Author Information

[Robin Daugherty](https://github.com/RobinDaugherty)
