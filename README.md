<!-- This was created with Claude Code -->

# Edge Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-Edge)


This directory contains Ansible automation for edge management and operations.

## Overview

The Edge automation provides playbooks and roles for managing and configuring
edge infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [container_lifecycle](roles/container_lifecycle/README.md) | Role for container lifecycle |
| [kiosk_mode](roles/kiosk_mode/README.md) | Role for kiosk mode |
| [shadowman_edge_simulation](roles/shadowman_edge_simulation/README.md) | Role for shadowman edge simulation |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| edgeprocesscontrol.yml | Playbook for edgeprocesscontrol | {{ vm_name | default('all')}} |
| provision_kiosk.yml | Playbook for provision kiosk | {{ vm_name | default('all')}} |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run edgeprocesscontrol.yml

# Run in stdout mode
ansible-navigator run edgeprocesscontrol.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - container_lifecycle
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-Edge/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
