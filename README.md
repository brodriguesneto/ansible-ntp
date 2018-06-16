ntp
===

[![Build Status](https://travis-ci.org/everproven/ansible-ntp.svg?branch=master)](https://travis-ci.org/everproven/ansible-ntp)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-everproven.ntp-blue.svg)](https://galaxy.ansible.com/everproven/ntp/)

An Ansible role that installs and configures [NTP] service on Linux and sets Timezone.

Platforms
---------

Role tested on Linux operating systems:

* Ubuntu Server 18.04 LTS
* Ubuntu Server 16.04 LTS

Requirements
------------

None.

Role Variables
--------------

__ntp_servers__: The NTP pool servers to synchronize from with its default value.

```YAML
ntp_servers:
  - a.ntp.br
  - b.ntp.br
  - c.ntp.br
```

__ntp_timezone__: The Timezone to configure system-wide with its default value.

```YAML
ntp_timezone: America/Sao_Paulo
```

> The cron service will be reloaded every time the Timezone changes.

Dependencies
------------

None.

Example Playbook
----------------

```YAML
- hosts: all
  become: True
  roles:
  - role: everporven.ntp
    ntp_timezone: America/Sao_Paulo
    ntp_servers:
      - 0.br.pool.ntp.org
      - 1.br.pool.ntp.org
      - 2.br.pool.ntp.org
```

License
-------

[Apache License 2.0]

Author Information
------------------

[Ever Proven]

[NTP]: https://en.wikipedia.org/wiki/Network_Time_Protocol
[Cron]: https://en.wikipedia.org/wiki/Cron
[Apache License 2.0]: https://github.com/everproven/ansible-ntp/blob/master/LICENSE
[Ever Proven]: https://github.com/everproven
