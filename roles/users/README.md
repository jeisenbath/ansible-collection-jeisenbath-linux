jeisenbath.linux.users
=========

Manage lists of Linux local users.
Compatible with Ansible >= 2.9

Role Variables
--------------

Variable users_linux, a list of users to manage.
Each list item is a dictionary of properties.
Some properties have defaults and may be omitted (noted in examples below).

```yaml
users_linux:
- name: ansible
  uid: "{{ ansible_user_id }}"
  sysuser: false # default false
  state: present # default present
  primary_group: ansible
  secondary_groups: # default omit
    - wheel
  authorized_keys: ansible_authorized_keys # default omit
```

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
        - role: jeisenbath.linux.users
          users_linux:
            - name: jeisenbath
              uid: 1005
              primary_group: jeisenbath
              secondary_groups:
                - ansible
                - sysadmin
              sysuser: false
              state: present
```

License
-------

GPL-3.0-or-later

