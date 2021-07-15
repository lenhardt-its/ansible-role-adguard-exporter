# Ansible Role: AdguardHome Exporter

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-adguard-exporter?style=flat)](https://github.com/OnkelDom/ansible-role-adguard-exporter/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-adguard-exporter.svg?style=flat)](https://github.com/OnkelDom/ansible-role-adguard-exporter/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-adguard-exporter/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-adguard-exporter)

## Description

Deploy and manage [AdGuardHome Exporter](https://github.com/AdguardTeam/AdGuardHome) service using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables for Client|
| `adguard_exporter_version` | 1.13 | AdGuard-Exporter package version. Also accepts `latest` as parameter. |
| `adguard_exporter_binary_install_dir` | /usr/local/bin | Binary install dir |
| `adguard_exporter_system_user` | "{{ prometheus_user \| default('adguard_exporter') }}" | Service User |
| `adguard_exporter_system_group` | "{{ prometheus_group \| default('adguard_exporter') }}" | Serviceuser Group |
| `adguard_exporter_web_listen_port` | 3200 | Port on which adguard-exporter will be listening |
| `adguard_exporter_web_listen_address` | 0.0.0.0 | Address on which adguard-exporter will be listening |
| `adguard_exporter_scrape_interval` | 60s | Interval of time the exporter will fetch data from Adguard |
| `adguard_exporter_log_limit` | 1000 | Limit for the return log data |
| `adguard_exporter_adguard_protocol` | http | Protocol to use to query Adguard |
| `adguard_exporter_adguard_username` | "" | Username to login to Adguard Home |
| `adguard_exporter_adguard_password` | "" | Password defined on the Adguard interface |
| `adguard_exporter_adguard_port` | 3200 | Port to use to communicate with Adguard API |

## Example
```yaml

```

### Playbook

```yaml
- hosts: all
  roles:
    - onkeldom.adguard_exporter
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
