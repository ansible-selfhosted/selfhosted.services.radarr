[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Copier](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/copier-org/copier/master/img/badge/badge-grayscale-inverted-border.json)](https://github.com/copier-org/copier)
[![Podman Badge](https://img.shields.io/badge/Podman-892CA0?logo=podman&logoColor=white)](https://podman.io/)
[![Hatch project](https://img.shields.io/badge/%F0%9F%A5%9A-Hatch-4051b5.svg)](https://github.com/pypa/hatch)
![CI](https://github.com/ansible-selfhosted/selfhosted.services.radarr/actions/workflows/ci.yml/badge.svg)
[![Ansible](https://img.shields.io/badge/Ansible-Molecule-EE0000?style=plastic&logo=ansible&logoColor=white)](https://github.com/ansible/molecule)

<!-- BEGIN_ANSIBLE_DOCS -->

# Ansible Role: [radarr](https://wiki.servarr.com/en/radarr)

A role to deploy Radarr using rootless Podman with systemd.

## Role Requirements

- none

*Refer to services collection for general requirements*

## Role Arguments

|Option|Description|Type|Required|Default|choices|
|---|---|---|---|---|---|
|radarr_additional_options|List of additional key=value for the quadlet container<br>ex: - "Network=custom.network"<br>Can also be used to leave comments by preceding with a '#'|list|False|[]|
|radarr_config_label|The labels for to the radarr config directory<br>Comma separated values (ex: rw,Z)|str|False||
|radarr_config_path|The path to the radarr configuration directory|str|False|~/.config/radarr/|
|radarr_data_label|The labels for to the radarr data directory<br>Comma separated values (ex: rw,Z)|str|False||
|radarr_data_path|The path to the radarr data directory<br>It is recommended to share the same data directory with other media managing services|str|False|~/.local/share/containers/storage/media|
|radarr_puid|The user id to run the inside the radarr container|int|False|1000|
|radarr_pgid|The group id to run the inside the radarr container|int|False|1000|
|radarr_timezone|The timezone for the radarr service|str|False|Etc/UTC|
|radarr_version|The version of the radarr container|str|False|latest|<ul><li>latest</li><li>develop</li><li>nightly</li></ul>
|radarr_web_port|The port for the web server|int|False|7878|


## Example Playbook

```
- hosts: all
  tasks:
    - name: Importing radarr role
      ansible.builtin.import_role:
        name: selfhosted.services.radarr
      vars:
```

## License

This project is licensed under the [MIT License](LICENSE)


⊂(▀¯▀⊂)

<!-- END_ANSIBLE_DOCS -->
