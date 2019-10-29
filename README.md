# Dubzland: Proxmox
[![Gitlab pipeline status (self-hosted)](https://img.shields.io/gitlab/pipeline/jdubz/dubzland-proxmox?gitlab_url=https%3A%2F%2Fgit.dubzland.net)](https://git.dubzland.net/jdubz/dubzland-proxmox/pipelines)

Installs and configures [Proxmox VE](https://proxmox.com).

## Requirements

Ansible version 2.0 or higher.

## Role Variables

Available variables are listed below, along with their default values (see
    `defaults/main.yml` for more info):

### dubzland_proxmox_iscsi_prefix

```yaml
dubzland_proxmox_iscsi_prefix: "2018-05.net.dubzland"
```

Specifies the prefix to use when determining the iSCSI initiator name to use for
a node.  For instance, given the above value, and a node named `proxmox01`, the
full initiator name would be `iqn.2018-05.net.dubzland`.

## Dependencies

None

## Example Playbook

```yaml
- hosts: proxmox-servers
  become: yes
  roles:
  - role: dubzland-proxmox
    vars:
      dubzland_proxmox_iscsi_prefix: "2019-01.com.mydomain"
```

## License

MIT

## Author

* [Josh Williams](https://codingprime.com)
