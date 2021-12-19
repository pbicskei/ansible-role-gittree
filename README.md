Role Name
=========

This role will fill a directory with git repository content, which can be split by:

- No split, all repos in {{ repository_base_path }}
- Project: {{ repository_base_path }}/{{ project }}
- Source: {{ repository_base_path }}/{{ source }}
- User: {{ repository_base_path }}/{{ user }}

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

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```bash
    - hosts: servers

      vars:
        repository_base_path: ~/workdir

        ssh_repositories:
          - { project: evil-ansible, source: github.com, user: pbicskei, name: ansible-role-template }
        
        split_by_project: false
        split_by_source: false
        split_by_user: false

      roles:
         - pbicskei.git_tree
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
