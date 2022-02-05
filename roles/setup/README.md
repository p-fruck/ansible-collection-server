Setup
=========

A quick, basic setup of your server

Requirements
------------

### Ansible Roles:

- `ansible.posix`

### Python packages on target machine:

- `selinux`

Role Variables
--------------

<table>
<thead>
<tr>
<th>Variable</th>
<th>Default value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>use_epel</td>
<td>True</td>
<td>Enable/Disable the Extra Packages for Enterprise Linux (EPEL)</td>
</tr>
<tr>
<td>packages</td>
<td><ul>
<li>cockpit</li>
<li>cockpit-podman</li>
<li>firewalld</li>
<li>htop</li>
<li>nano</li>
<li>podman</li>
<li>podman-plugins</li>
<li>wget</li>
</ul></td>
<td>Packages to install during setup</td>
</tr>
<tr>
<td>users</td>
<td>[]</td>
<td>A list of users to create. Each user is an object of the form:
<pre lang="yaml">
- name: username
  password: `pw_hash`
  groups:
    - ssh
    - wheel
</pre></td>
</tr>
<tr>
<td>firewall_services</td>
<td>[]</td>
<td>A list of services to open in the firewall. Example:
<pre lang="yaml">
firewall_services:
  - http
  - https
  - ssh
</pre></td>
</tr>
<tr>
<td>firewall_ports</td>
<td>[]</td>
<td>A list of ports to open in the firewall. Example:
<pre lang="yaml">
firewall_ports: [ 8080, 8443 ]
</pre></td>
</tr>
<tr>
<td>firewall_forward_ports</td>
<td>[]</td>
<td>A list of ports to forward with the given offset.
This comes in useful if you want to expose an unprivileged service on a privileged port.</td>
</tr>
<tr>
<td>firewall_forward_ports_offset</td>
<td>10000</td>
<td>The offset to forward ports specified in `firewall_forward_ports`. Example:
<pre lang="yaml">
firewall_forward_ports: [ 80, 443 ]
firewall_forward_ports_offset: 10000
</pre>
This config will redirect the privileged port 80 to the unprivileged port 10080 as well as 443 to 10443.</td>
</tr>
</tbody>
</table>

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
