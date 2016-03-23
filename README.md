# ansible-newrelic-coreos

This ansible role installs and configures the New Relic Server Agent (System Monitor Daemon) on CoreOS via Docker.

## Requirements

This role requires Ansible 1.2 higher and platforms listed in the metadata file.

## Role Variables

The variables that can be passed to this role and a brief description about them are as follows

    # License key
    newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16

    newrelic_image: "newrelic/nrsysmond:latest"


## Examples

### Paramaterized Role

    ---
    - hosts: all
      roles:
        - { role: newrelic, newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16 }

### Vars

    ---
    - hosts: all
      vars:
        newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16
      roles:
        - newrelic

### Group vars

#### group_vars/production

    ---
    newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16

#### site.yml

    ---
    - hosts: all
      roles:
        - newrelic