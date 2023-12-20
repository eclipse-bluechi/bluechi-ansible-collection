# Eclipse BlueChi Ansible Collection

## Overview

Use this Ansible Collection to provision [BlueChi](https://bluechi.readthedocs.io/en/latest/) on your system

## Requirements

### Ansible Version

This collection requires ansible from version `2.14.0` and above

### Collections

This collection depends on the following collections:
- community.general: "*"

## Roles

These are the roles included in the collection. Follow the links below to see the detailed documentation for each role.

- [`controller`](./roles/controller/README.md) - Install and configure the `BlueChi Controller`
- [`agent`](./roles/agent/README.md) - Install and configure the `BlueChi Agent`
- [`common`](./roles/common/README.md) - Used for common tasks. Not intended to be used standalone

## Installation Playbook

The collection includes a [playbook](./playbooks/install.yml) for installation.

To use the installer playbook create an inventory file indicating the different machine types - `bluechi_controller` and `bluechi_agents`.
Please note that `bluechi_controller` assumes both `controller` and `agent` roles. So, there is no need to list it twice.

### Sample Inventory

```yaml
all:
  hosts:
  children:
    bluechi_controller:
      hosts:
        controller.example.com:
    bluechi_agents:
       hosts:
         agent-1.example.com:
         agent-1.example.com:
```

### Using the installer

```bash
ansible-playbook -i  </path/to/inventory> eclipse_bluechi.bluechi.install
```

## Installing the collection from Ansible Galaxy

Before using this collection, you need to install it with the Ansible Galaxy command-line tool:

```bash
ansible-galaxy collection install eclipse_bluechi.bluechi
```

You can also include it in a `requirements.yml` file and install it with `ansible-galaxy collection install -r requirements.yml`, using the format:

```yaml
---
collections:
  - name: eclipse_bluechi.bluechi
```

Note that if you install the collection from Ansible Galaxy, it will not be upgraded automatically when you upgrade the `ansible` package.
To upgrade the collection to the latest available version, run the following command:

```bash
ansible-galaxy collection install eclipse-bluechi.bluechi --upgrade
```

You can also install a specific version of the collection.
For example, if you need to downgrade when something is broken in the latest version (please report an issue in this repository).
Use the following syntax to install version `1.0.0`:

```bash
ansible-galaxy collection install eclipse-bluechi.bluechi:==1.0.0
```

See [Using Ansible collections](https://docs.ansible.com/ansible/devel/user_guide/collections_using.html) for more details.

## Contributing

We appreciate participation from any new contributors. Get started by opening an issue or pull request. Refer to our [contribution guide](./CONTRIBUTING.md) for more information.

## Reporting issues

Please open a [new issue](https://github.com/eclipse-bluechi/bluechi-ansible-collection/issues/new/choose) for any bugs or security vulnerabilities you may encounter. We also invite you to open an issue if you have ideas on how we can improve the solution or want to make a suggestion for enhancement.

## Release notes

See the [changelog](https://github.com/eclipse-bluechi/bluechi-ansible-collection/tree/main/CHANGELOG.rst).

## Licensing

See [LICENSE](./LICENSE) to see the full text.
