<!-- This was created with Claude Code -->

container_lifecycle
===================

An Ansible role for container lifecycle.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **systemd_units_dir**: defaults file for container_lifecycle
  - Default: `/etc/systemd/system/`

* **service_name**: Variable used in: Gather information about the current running container

* **container_state**: Variable used in: Install Transction
  - Default: `installed`

* **container_image**: Variable used in: Pull down container image

* **container_tag**: Variable used in: {{ container_image }}

* **container_port_mapping**: Network port number

* **container_healthcheck**: Check mode or validation flag

* **container_healthcheck_interval**: Time interval
  - Default: `30s`

* **container_healthcheck_retries**: Number of retry attempts
  - Default: `5`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: container_lifecycle
      vars:
        systemd_units_dir: <value>
        service_name: <value>
        container_state: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
