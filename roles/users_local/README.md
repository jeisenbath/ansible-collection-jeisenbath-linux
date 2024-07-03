jeisenbath.linux.users_local
=========

Manage lists of Linux local users and groups.
Compatible with Ansible >= 2.9

Role Variables
--------------

Variables users_local and groups_local, each a list of users and groups to manage.
Each list item is a dictionary of properties.
Some properties have defaults and may be omitted (noted in examples below).

groups_local:
- name: ansible
  gid: "{{ ansible_group_id }}"
  sysgroup: true # default false
  state: present # default present
  sudoers_file: ansible_sudoers # default omit

users_local:
- name: ansible
  uid: "{{ ansible_user_id }}"
  sysuser: false # default false
  state: present # default present
  primary_group: ansible
  secondary_groups: # default omit
    - wheel
  authorized_keys: ansible_authorized_keys # default omit

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: jeisenbath.linux.users_local
          users_local:
            - name: ansible
              uid: 10255
              primary_group: ansible
              sysuser: false
              authorized_keys: "{{ ansible_auth_keys_path }}"
              state: present
            - name: jeisenbath
              uid: 1005
              primary_group: jeisenbath
              secondary_groups:
                - ansible
                - sysadmin
              sysuser: false
              state: present
          groups_local:
            - name: ansible
              gid: 10255
              sysgroup: true
              sudoers_file: ansible_sudoers
            - name: sysadmin
              gid: 61999
              sysgroup: true
              sudoers_file: "{{ sysadmin_sudoers_path }}
             

License
-------

GPL-3.0-or-later

