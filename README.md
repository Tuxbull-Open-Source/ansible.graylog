# Graylog single-node lab role

Install Graylog 7.2, MongoDB 8.0, and Graylog Data Node on a single Rocky Linux
10 host. Rocky 10 use is explicitly user-authorized for this lab role; consult
Graylog's current compatibility matrix before production use.

## Requirements

- Rocky Linux 10 lab host with at least 6 vCPU, 16 GiB RAM, and 50 GB disk.
- A secret `graylog_admin_password` at least 12 characters long, supplied from
  Ansible Vault or an approved secret manager.

## Example

```yaml
- hosts: graylog_lab
  become: true
  vars_files: [vault.yml]
  roles:
    - role: tuxbull.graylog
      vars:
        graylog_admin_password: "{{ vault_graylog_admin_password }}"
```

## Scope and limitations

The role creates a local MongoDB/Data Node/Graylog deployment and waits for the
local Graylog API. It deliberately does not configure TLS, Nginx, firewalld
exposure, mail, external inputs, dashboards, backup, or HA. Treat it as an
explicitly authorized lab setup, not a production reference architecture.
