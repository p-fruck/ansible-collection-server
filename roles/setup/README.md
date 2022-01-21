Setup
=========

A quick, basic setup of your server

Requirements
------------

- `ansible.posix`

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: servers
      gather_facts: true
      vars:
        users:
          - name: username
            password: <your_password_hash> # [learn more](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/user_module.html#parameter-password)
            groups:
              - ssh
              - wheel
      roles:
        - pfruck.server.setup

License
-------

GPL-3.0

Author Information
------------------

This role was created in 2022 by [Philipp Fruck](p-fruck.eu).

#### Maintainer(s)

- [Philipp Fruck](https://github.com/p-fruck)
