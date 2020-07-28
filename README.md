# About

Ansible role `ansible-pganalyze-collector`
Install, setup and run pganalyze-collector for PostgreSQL as systemd service for VM and BareMetal servers..

pganalyze-collector is SaaS monitoring agent for PostgreSQL.

## Requirements

- postgresql
- systemd

## Role variables

### Defaults

```yaml
dpkg_force_overwrite_configs: false

pganalyze_package: pganalyze-collector
pganalyze_version: latest

pganalyze_user: pganalyze
pganalyze_group: pganalyze

pganalyze_service_state: restarted

pganalyze_api_key: "YOUR_ORGANIZATION_APIKEY"
pganalize_server_api_key: "CURRENT_SERVER_APIKEY"
pganalyze_db_name: "*"
pganalyze_db_user: "{{ pganalyze_user }}"
pganalyze_db_password: ""

pganalyze_servers:
  - name: "{{ ansible_hostname }}"
    api_key: "{{ pganalize_server_api_key }}"
    db_name: "{{ pganalyze_db_name }}"
    db_username: "{{ pganalyze_db_user }}"
    db_password: "{{ pganalyze_db_password }}"
    db_host: 127.0.0.1
    db_port: 5432
```

## Dependencies

-

## Example playbook

```yaml
- hosts: servers
  roles:
    - role: ansible-pganalyze-collector
```

## License

MIT
