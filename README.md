Ansible role for command-line-tools
==================================

Installs a pinned version of command line tools for macos

[![GitHub Actions](https://github.com/mongodb-ansible-roles/ansible-role-command-line-tools/workflows/Molecule%20Test/badge.svg)](https://github.com/mongodb-ansible-roles/ansible-role-command-line-tools/actions?query=workflow%3A%22Molecule+Test%22)
[![GitHub Actions](https://github.com/mongodb-ansible-roles/ansible-role-command-line-tools/workflows/Release/badge.svg)](https://github.com/mongodb-ansible-roles/ansible-role-command-line-tools/actions?query=workflow%3A%22Release%22)

Requirements
------------

Must be on run on a MacOS system

Role Variables
--------------

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-------:|:--------:|
| command\_line\_tools\_dest | Where to download the Command Line Tools dmg | string | /var/root/osx-command-line-tools.dmg | false |
| command\_line\_tools\_force\_install | Whether to replace any currently installed Command Line Tools | boolean | false | false |
| command\_line\_tools\_mount\_path | Where to mount the Command Line Tools dmg | string | /Volumes/osx-command-line-tools | false |
| command\_line\_tools\_url | Url to download the Command Line Tools dmg from | string | {{ command\_line\_tools\_version\_urls[macos\_full\_version] }} | false |

Testing
-------

There are 2 ways of testing this role:
1. GitHub Actions: GitHub Actions will run Molecule tests on the `macos-latest` runner that is offered by GitHub.
2. Locally: Run `molecule test` will run the default scenario

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ansible-role-command-line-tools
```

License
-------

[Apache License](LICENSE)
