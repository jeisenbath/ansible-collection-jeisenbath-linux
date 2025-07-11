jeisenbath.linux.interfaces
=========

Configure network interfaces on a linux server.

Role Variables
--------------

This role takes a list of dicts as the variable 'interfaces_ethernet_interfaces'
```yaml
interfaces_ethernet_interfaces:
  - conn_name: ens192
    ifname: # defaults to conn_name when undefined
    autoconnect: # default true
    ip4: # format in 'ip address/cidr' i.e. 192.168.0.1/24
    gw4: # mutually exclusive with never_default4
    never_default4: # mutually exclusive with gw4
    may_fail4: false # module default is true, set false if required before network-online.target
    dns4: # list of up to 3 dns servers
      - 127.0.0.1
      - "{{ primary_dns }}"
      - "{{ secondary_dns }}"
    dns4_search: # list of dns search domains
      - search_domain
    dns4_options:
      - list of options
    method6: # default 'ignore'
```


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```yaml
- hosts: webservers
  roles:
    - role: jeisenbath.linux.interfaces
      interfaces_ethernet_interfaces:
        - conn_name: ens224
          ip4: 10.0.0.10/24
          never_default4: true
          may_fail4: false
        - conn_name: ens192
          ip4: "192.168.0.10/24"
          gw4: "192.168.0.1"
          may_fail4: false
          dns4_search: localhost.localdomain
          dns4:
            - 127.0.0.1
            - 8.8.8.8
            - 8.8.4.4

```

License
-------

GPL-3.0-or-later

Author Information
------------------

Josh Eisenbath (@jeisenbath)
