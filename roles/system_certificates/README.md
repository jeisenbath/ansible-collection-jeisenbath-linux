system_certificates
=========

Manage system shared certificates.

Role Variables
--------------

```yaml
system_certificates_os_family: RedHat # default
system_certificates_install_list: # define to install certificates
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - role: jeisenbath.linux.system_certificates
      system_certificates_os_family: RedHat
      system_certificates_install_list:
        - "{{ playbook_dir }}/files/my_cert.crt"
```

License
-------

GPL-3.0-or-later
