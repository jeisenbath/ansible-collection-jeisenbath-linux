jeisenbath.linux.groups
=========

Manage lists of Linux local groups, and optionally sudoers files for those groups.
Compatible with Ansible >= 2.9

Role Variables
--------------

Variables linux_groups contains a list of groups to manage.
Each list item is a dictionary of properties.
Some properties have defaults and may be omitted (noted in examples below).

```yaml
linux_groups:
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
          linux_groups:
            - name: ansible
              gid: 10255
              sysgroup: true
              sudoers_file: ansible_sudoers
```
             

License
-------

GPL-3.0-or-later

