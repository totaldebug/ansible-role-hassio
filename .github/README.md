<h4 align="center">An Ansible role for creating a fully functional HASSIO Server with ha CLI.</h4>

<p align="center">
    <a href="https://github.com/totaldebug/ansible-role-hassio/commits/master">
    <img src="https://img.shields.io/github/last-commit/totaldebug/ansible-role-hassio.svg?style=flat-square&logo=github&logoColor=white"
         alt="GitHub last commit">
    <a href="https://github.com/totaldebug/ansible-role-hassio/issues">
    <img src="https://img.shields.io/github/issues-raw/totaldebug/ansible-role-hassio.svg?style=flat-square&logo=github&logoColor=white"
         alt="GitHub issues">
    <a href="https://github.com/totaldebug/ansible-role-hassio/pulls">
    <img src="https://img.shields.io/github/issues-pr-raw/totaldebug/ansible-role-hassio.svg?style=flat-square&logo=github&logoColor=white"
         alt="GitHub pull requests">
</p>

<p align="center">
  <a href="#configuration">Configuration</a> •
  <a href="#features">Features</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#author">Author</a> •
  <a href="#support">Support</a> •
  <a href="#donate">Donate</a> •
  <a href="#license">License</a>
</p>

---

## About

<table>
<tr>
<td>

**ansible-role-hassio** is a **high-quality** _Ansible Role_ that deploys **HASSIO** to your ansible clients.

Hass.io is an operating system that will take care of installing and updating Home Assistant, is managed from the Home Assistant UI, allows creating/restoring snapshots of your configuration and can easily be extended using Hass.io add-ons including Google Assistant and Let’s Encrypt.

**Note:** This Ansible role is currently only supported on Debian 10 as per hass.io documentation, it may work on other OS however I have not tested this.

</td>
</tr>
</table>

## Configuration

### Install

```shell
ansible-galaxy install totaldebug.hassio
```

### Role Variables

| **Input** | **Default** | **Description** |
|:---------:|:-----------:|:---------------:|
| `hassio_user` | `hassio` | Default user for running hassio |
| `hassio_group` | `hassio` | Default group for running hassio |
| `supervisor` | `homeassistant/amd64-hassio-supervisor` | Docker file to use for supervisor (changes based on OS Architecture) |
| `machine` | `qemux86-64` | Machine type (qemux86, qemux86-64, armv6l, armv7l, aarch64) |
| `hassio_share` | `/usr/share/hassio` | main configuration location |
| `hassio_version` | `latest` | Change the version if you want to deploy a specific one |
| `hassio_config` | `/etc/hassio.json` | Hassio Config File |
| `hassio_bin` | `/usr/sbin/hassio-supervisor` | binary location for hassio-supervisor |
| `docker_bin` | `/usr/bin/docker` | Docker binary location |

### Example Playbook

```yaml
---

- name: Install Hassio
  hosts: all
  become: yes
  gather_facts: no
  vars:
    - hassio_share: "/usr/share/hassio"   #Default
    - version: latest   #Default
  roles:
     - totaldebug.hassio

```

## Features

|                            |         🔰         |
| -------------------------- | :----------------: |
| Install Hassio                        |         ✔️         |
| Install hassio-supervisor service     |         ✔️         |
| Install hassio-apparmor service       |         ✔️         |

## Contributing

Got **something interesting** you'd like to **share**? Learn about [contributing](https://github.com/totaldebug/.github/blob/main/.github/CONTRIBUTING.md).

### Versioning

This project follows semantic versioning.

In the context of semantic versioning, consider the role contract to be defined by the role variables.

- Breaking Changes or changes that require user intervention will increase the major version. This includes changing the default value of a role variable.
- Changes that do not require user intervention, but add new features, will increase the minor version.
- Bug fixes will increase the patch version.

## Author

| [![TotalDebug](https://totaldebug.uk/assets/images/logo.png)](https://linkedin.com/in/marksie1988) |
|:--:|
| **marksie1988 (Steven Marks)** |

## Support

Reach out to me at one of the following places:

- via [Discord](https://discord.gg/6fmekudc8Q)
- Raise an issue in GitHub

## Donate

Please consider supporting this project by sponsoring, or just donating a little via [our sponsor page](https://github.com/sponsors/marksie1988)

## License

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-orange.svg?style=flat-square)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

- Copyright © [Total Debug](https://totaldebug.uk "Total Debug").
