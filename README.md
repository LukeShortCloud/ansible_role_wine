# ansible-role-wine

The "wine" Ansible role is a flexible role for installing different versions of Wine on many UNIX-like platforms.

## Requirements

Ansible >= 2.4

## Role Variables

* use_distro_packages = Install "wine" using the package provided by the operating system's package manage. If set to False, packages from WineHQ will be installed instead. Default: `True`.
* wine_release = On some supported systems, a specific release of Wine can be used. This can be set to "stable", "development", or "staging". Default: `development`.
* user_home = The home directory of the user that will be running Wine.

## Dependencies

None.

## Example Playbook

This example Playbook installs the latest Wine Staging release directly from WineHQ.

```
- hosts: localhost
  vars:
    use_distro_packages: False
    wine_release: staging
  roles:
   - ansible-role-wine
```

## License

GPLv3
