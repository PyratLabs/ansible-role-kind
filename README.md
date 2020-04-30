# Ansible Role: kind

Ansible role for installing kind.

[![Build Status](https://www.travis-ci.org/PyratLabs/ansible-role-kind.svg?branch=master)](https://www.travis-ci.org/PyratLabs/ansible-role-kind)

## Requirements

This role has been tested on Ansible 2.7.0+ against the following Linux Distributions:

  - Amazon Linux 2
  - CentOS 8
  - CentOS 7
  - Debian 10
  - Fedora 29
  - Fedora 30
  - Fedora 31
  - Ubuntu 18.04 LTS

## Disclaimer

If you have any problems please create a GitHub issue, I maintain this role in
my spare time so I cannot promise a speedy fix delivery.

## Role Variables


| Variable           | Description                                                              | Default Value    |
|--------------------|--------------------------------------------------------------------------|------------------|
| `kind_version`     | Use a specific version of kind, eg. `0.7.0`. Specify `false` for latest. | `false`          |
| `kind_install_dir` | Installation directory for kind.                                         | `$HOME/bin`      |

## Dependencies

No dependencies on other roles.

## Example Playbook

Example playbook for installing to single user:

```yaml
- hosts: workstation
  roles:
     - { role: xanmanning.kind, kind_version: 0.7.0 }
```

Example playbook for installing the latest kind version globally:

```yaml
---
- hosts: workstation
  become: true
  vars:
    kind_install_dir: /usr/local/bin
  roles:
    - role: xanmanning.kind
```

## License

[BSD 3-clause](LICENSE.txt)

## Author Information

[Xan Manning](https://xanmanning.co.uk/)
