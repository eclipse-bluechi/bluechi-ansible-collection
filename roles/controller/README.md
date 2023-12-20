# eclipse_bluechi.bluechi.controller role

The `controller` role handles the installation and configuration of the BlueChi Controller

## Requirements

### Installing on RHEL

When installing on RHEL, the machine should already be subscribed using the `subscription-manager`

## Role Variables

### `controller_allowed_nodes`

Comma separated list of the names of the `bluechi-agents` allowed to the connected to this `bluechi-controller`


## Example Playbook

```yaml
- name: Setup BlueChi Controller
  hosts: bluechi_controller
  become: true
  roles:
  - name: controller
    controller_allowed_nodes: "controller,node1,node2"
```
