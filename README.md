Ansible role for command-line-tools
==================================

Installs a pinned version of command line tools for macos

[![CircleCI](https://img.shields.io/circleci/build/github/mongodb-ansible-roles/ansible-role-command-line-tools/master?style=flat-square)](https://circleci.com/gh/mongodb-ansible-roles/ansible-role-command-line-tools)

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

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ansible-role-command-line-tools
```

Development
-----------

Testing this role locally requires the CircleCI [Local CLI](https://circleci.com/docs/2.0/local-cli/).

To install the CLI for macOS and Linux, invoke the following command:

    $ curl -fLSs https://circle.ci/cli | DESTDIR=/usr/local/bin bash

After installing the CLI, invoke the following command to run the Molecule tests:

    $ make test

License
-------

[Apache License](LICENSE)
