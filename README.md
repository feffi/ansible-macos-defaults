# ansible-macos-defaults

Ansible role to set macOS "defaults" settings.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-defaults.svg)](https://github.com/feffi/ansible-macos-defaults) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-defaults/total.svg)](https://github.com/feffi/ansible-macos-defaults) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-defaults.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-defaults) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-defaults.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-defaults) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-defaults.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-defaults) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-defaults/blob/master/LICENSE)

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
```
