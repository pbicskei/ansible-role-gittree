[![Release](https://github.com/pbicskei/ansible-role-gittree/actions/workflows/release.yml/badge.svg)](https://github.com/pbicskei/ansible-role-gittree/actions/workflows/release.yml)

Role Name
=========

This role will fill a directory with git repository content, which can be split by:

- No split, all repos in {{ clone_path }}
- Project: {{ clone_path }}/{{ project }}
- Source: {{ clone_path }}/{{ source }}
- User: {{ clone_path }}/{{ user }}

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Ensure you have the role installed:

```bash
ansible-galaxy role install pbicskei.gittree
```

create a `play.yml`.

```yaml
    - hosts: servers

      vars:
        clone_path: ~/workdir

        ssh_repositories:
          - { project: evil-ansible, source: github.com, user: pbicskei, name: ansible-role-template version: develop }
          - { project: evil-ansible, source: github.com, user: pbicskei, name: ansible-role-gittree version: main }
        
        split_by_project: false
        split_by_source: false
        split_by_user: false

      roles:
         - pbicskei.gittree
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
