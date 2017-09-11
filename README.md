# ansible-macos-defaults

Ansible role to set macOS "defaults" settings.

[![Build Status](https://travis-ci.org/feffi/ansible-macos-defaults.svg?branch=master)](https://travis-ci.org/feffi/ansible-macos-defaults)

## Requirements

* maxOS >= 10.10
* Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-defaults.git
  name: feffi.macos-defaults
```


## Role Variables

```yaml
macos_defaults: {
  defaults: [
    { domain: "com.apple.ActivityMonitor", key: "IconType", type: "integer", value: "5" },
    { domain: "com.apple.ActivityMonitor", key: "OpenMainWindow", type: "boolean", value: "true" },
    { domain: "com.apple.ActivityMonitor", key: "SortColumn", type: "string", value: "CPUUsage" },
    { domain: "com.apple.dock", key: "expose-animation-duration", type: "float", value: "0.12" }
  ]
}
```

## Example Playbook

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-defaults }
``
