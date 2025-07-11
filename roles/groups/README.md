jeisenbath.linux.groups
=========

Manage lists of Linux local groups, and optionally sudoers files for those groups.
Compatible with Ansible >= 2.9

Role Variables
--------------

Variables groups_linux contains a list of groups to manage.
Each list item is a dictionary of properties.
Some properties have defaults and may be omitted (noted in examples below).

```yaml
groups_linux:
  - name: ansible
    gid: "{{ ansible_group_id }}"
    sysgroup: true # default false
    state: present # default present
    sudoers_file: ansible_sudoers # default omit
```

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
        - role: jeisenbath.linux.groups
          groups_linux:
            - name: jeisenbath
              gid: 10201
```
             
License
-------

GPL-3.0-or-later

