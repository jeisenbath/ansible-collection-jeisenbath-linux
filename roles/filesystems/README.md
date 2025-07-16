jeisenbath.linux.filesystems
=========

A role to manage volume groups, logical volumes, filesystems and mounts.

Requirements
------------

community.general
ansible.posix

Role Variables
--------------

Optional variables
```yaml
filesystems_vgs:
  - vg: # required
    pvs: # required, comma separated list
    pesize: # optional
    pv_options: # optional
    vg_options: # optional
    state: # default 'present'
    force: # optional
    pvresize: # optional
    remove_extra_pvs: # optional
    reset_vg_uuid: # optional
    reset_pv_uuid: # optional
filesystems_lvols:
  - lv: # required unless creating a thinpool
    vg: # required
    size: # optional
    active: # optional
    force: # optional
    opts: # optional
    pvs: # optional
    resizefs: # optional
    shrink: # optional
    snapshot: # optional
    state: # default 'present'
    thinpool: # optional
filesystems:
  - dev: # required
    force: # optional
    fstype: # optional
    opts: # optional
    resizefs: # optional
    state: # default 'present'
    uuid: # optional
filesystems_mounts:
  - path: # required
    state: # required
    backup: # optional
    boot: # optional
    dump: # optional
    fstab: # optional
    fstype: # optional
    opts: # optional
    opts_no_log: # optional
    passno: # optional
    src: # optional
    owner: # optional
      user: # required if owner is defined
      group: # required if owner is defined
      mode: # default '0755'
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - role: jeisenbath.linux.filesystems
      filesystems_vgs:
        - vg: vg_opt
          pvs: /dev/sda1,/dev/sda2
      filesystems_lvols:
        - lv: lv_opt
          vg: vg_opt
          size: 100g
          shrink: false
      filesystems:
        - dev: /dev/mapper/vg_opt-lv_opt
          fstype: xfs
      filesystems_mounts:
        - path: /opt
          src: /dev/mapper/vg_opt-lv_opt
          fstype: xfs
          state: mounted
          owner:
            user: admin
            group: wheel
            mode: '0750'
```

License
-------

GPL-3.0-or-later
