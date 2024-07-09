# Ansible Role: Red Hat Satellite Installation

This Ansible role automates the installation and configuration of Red Hat Satellite on a Red Hat Enterprise Linux (RHEL) server. The role performs the following tasks:

1. Registers the system with Red Hat Subscription Manager.
2. Disables all RHSM repositories.
3. Enables required RHSM repositories.
4. Ensures all packages are updated.
5. Enables the Satellite module.
6. Installs Satellite packages.
7. Ensures required services are enabled and started.
8. Configures firewall rules to allow necessary ports.
9. Installs and configures Red Hat Satellite.
10. Reboots the server to apply changes.

## Requirements

- Ansible 2.9 or higher
- Community General Collection
- Ansible POSIX Collection

## Role Variables

The following variables can be customized to suit your needs:

| Variable                       | Description                                                              | Default Value            |
|--------------------------------|--------------------------------------------------------------------------|--------------------------|
| `rhsm_user`                    | Red Hat Subscription Manager username                                    | N/A (must be provided)   |
| `rhsm_password`                | Red Hat Subscription Manager password                                    | N/A (must be provided)   |

## Example Playbook

Here is an example of how to use this role in a playbook:

```yaml
- hosts: satellite
  become: yes
  vars:
    rhsm_user: "your_rhsm_username"
    rhsm_password: "your_rhsm_password"
  roles:
    - redhat_satellite_installation
