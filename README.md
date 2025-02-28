# Ansible RHEL9 Local Repo

Ansible role to create a local patching repository

## Requirements

A Red Hat Enterprise Linux 9 server connected to RHSM with atleast 400GB of availible drive space in /var

### Collections

- community.general

## Role Variables

N/A

## Example Inventory

```yaml
---
infrastructure:
  children:
    patching:
      hosts:
        patch.local.domain:
            ansible_user: user
            ansible_host: 10.10.1.90
```

## Example Playbook

`ansible-playbook -i inventory.yml create-patch-repo.yml -K`

```yaml
---
- name: Create a Local RHEL 9 Patching Repository Server
  hosts: patching
  become: true
  roles:
    - { role: rhel9_localrepo }
```

## License

MIT

## Author Information

[Chad Zimmerman](https://github.com/PrymalInstynct)
