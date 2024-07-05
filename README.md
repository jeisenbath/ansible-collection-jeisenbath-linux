# Ansible Collection - jeisenbath.linux

Documentation for the collection.

# Ansible Collection - jeisenbath.vmware

Documentation for the collection.

<!--start collection content-->
### Roles
| Name                        | Description                   |
|-----------------------------|-------------------------------|
| jeisenbath.linux.users_local | Manage local users and groups |

### Installing the Collection from Ansible Galaxy

Before using this collection, you need to install it with the Ansible Galaxy command-line tool:
```bash
ansible-galaxy collection install git+https://github.com/jeisenbath/ansible-collection-jeisenbath-linux.git
```

You can also include it in a `requirements.yml` file and install it with `ansible-galaxy collection install -r requirements.yml`, using the format:
```yaml
---
collections:
  - name: jeisenbath.vmware
    type: git
    source: https://github.com/jeisenbath/ansible-collection-jeisenbath-linux
```

Note that if you install the collection from Ansible Galaxy, it will not be upgraded automatically when you upgrade the `ansible` package. To upgrade the collection to the latest available version, run the following command:
```bash
ansible-galaxy collection install git+https://github.com/jeisenbath/ansible-collection-jeisenbath-linux.git --upgrade
```

You can also install a specific version of the collection, for example, if you need to downgrade when something is broken in the latest version (please report an issue in this repository). Use the following syntax to install version `1.0.0`:

```bash
ansible-galaxy collection install git+https://github.com/jeisenbath/ansible-collection-jeisenbath-linux.git,v1.0.0
```

See [Ansible Using collections](https://docs.ansible.com/ansible/devel/user_guide/collections_using.html) for more details.

## Licensing

<!-- Include the appropriate license information here and a pointer to the full licensing details. If the collection contains modules migrated from the ansible/ansible repo, you must use the same license that existed in the ansible/ansible repo. See the GNU license example below. -->

GNU General Public License v3.0 or later.

See [LICENSE](https://www.gnu.org/licenses/gpl-3.0.txt) to see the full text.
