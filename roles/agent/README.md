# eclipse_bluechi.bluechi.agent role

The `agent` role handles the installation and configuration of the BlueChi Agent

## Requirements

### Installing on RHEL

When installing on RHEL, the machine should already be subscribed using the `subscription-manager`

## Role Variables

### `agent_node_name`

Name of the `bluechi-agent` as listed in the `AllowedNodeNames` list of the `bluechi-controller`

### `agent_controller_host`

Host Address of the `bluechi-controller` the agent should connect to.
Used to set `ManagerHost`.

### `agent_controller_port`

Port number of the `bluechi-controller` the agent should connect to
Used to set `ManagerPort`.

### `agent_controller_address`

SD Bus address of the `bluechi-controller` the agent should connect to
Used to set `ManagerAddress`

## Example Playbook

```yaml
- name: Setup Agents
  hosts: bluechi_agents
  become: true
  roles:
  - name: agent
    agent_controller_host: 172.16.0.5
```
