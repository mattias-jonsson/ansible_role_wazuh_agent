# Ansible Role: wazuh_agent

This Ansible role installs and upgrades the Wazuh agent on Ubuntu 22.04 and 24.04.

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see `defaults/main.yml`):

## Role Variables

Variables enable customization of the Wazuh agent's installation. Below is a comprehensive list of variables you can configure:

| Variable                              | Required | Default | Description |
|---------------------------------------|----------|---------|-------------|
| `wazuh_agent_manager`         | Yes       | | The hostname or IP address of the Wazuh manager. |
| `wazuh_agent_package_hold`      | No       | `false` | Determines whether the Wazuh agent package should be held (prevented from upgrading). |
| `wazuh_agent_repository_key_url`   | No      | `{{ wazuh_agent_repository_url }}/key/GPG-KEY-WAZUH` | The URL pointing to the GPG key file for the Wazuh package repository. |
| `wazuh_agent_repository_url`             | No      | `https://packages.wazuh.com` | The base URL of the Wazuh agent package repository. |
| `wazuh_agent_version_pattern` | No     | `4.x` | The version pattern to be used for the Wazuh agent package repository. |
These variables are defined in the `defaults/main.yml` file.

Dependencies
------------

This role has no external dependencies.

Example Playbook
----------------

    - hosts: servers

      vars:
        wazuh_agent_manager: 10.0.0.1

      roles:
        - wazuh_agent

License
-------

MIT

Author Information
------------------

Mattias Jonsson
