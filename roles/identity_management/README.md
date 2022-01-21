Identity Management
=========

Setup Keycloak as Podman container in conjunction with 389ds and Cockpit on the host system.

Requirements
------------

Must be run on a RHEL derivative.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: servers
      vars:
        ds_suffix: "dc=my,dc=domain"
      roles:
        - pfruck.server.identity_management

License
-------

GPL-3.0

Author Information
------------------

This role was created in 2022 by [Philipp Fruck](p-fruck.eu).

#### Maintainer(s)

- [Philipp Fruck](https://github.com/p-fruck)
