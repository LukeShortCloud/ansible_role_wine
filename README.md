# ansible_role_wine

The "wine" Ansible role is a flexible role for installing different versions of Wine on many UNIX-like platforms.

## Requirements

Ansible >= 2.7

## Role Variables

* use_distro_packages = Install "wine" using the package provided by the operating system's package manage. If set to False, packages from WineHQ will be installed instead. Default: `True`.
    * WineHQ only provides packages for these Linux distributions: Debian, Fedora, and Ubuntu.
* user_home = The home directory of the user that will be running Wine. Default: `{{ ansible_user_dir }}`.
* wine_install_dependencies = Install recommended/optional packages for Wine. Default: `True`.
* wine_install_build_dependencies = Install packages required to build Wine from source code. Default: `False`.
* wine_release = On some supported systems, a specific release of Wine can be used. This can be set to "stable", "development", or "staging". Default: `development`.

## Dependencies

None.

## Example Playbook

This example Playbook installs the latest Wine Staging release directly from WineHQ.

```
- hosts: localhost
  roles:
    - name: ansible_role_wine
      vars:
        use_distro_packages: False
        wine_release: staging
```

## License

GPLv3
