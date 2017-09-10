# ansible-osx-defaults

Ansible role to set macOS "defaults" settings.

[![Build Status](https://travis-ci.org/feffi/ansible-osx-defaults.svg?branch=master)](https://travis-ci.org/feffi/ansible-osx-defaults)

## Requirements

* maxOS >= 10.10
* Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```
- src: https://github.com/feffi/ansible-osx-defaults.git
  name: feffi.osx-defaults
```


## Role Variables

```yaml
# Setup OSX defaults. Also see: https://github.com/osxstrap/osxstrap-config-base/blob/master/config/osx-defaults.yml
osx_defaults: {
  defaults: [
    { domain: "com.apple.ActivityMonitor", key: "IconType", type: "integer", value: "5" },
    { domain: "com.apple.ActivityMonitor", key: "OpenMainWindow", type: "boolean", value: "true" },
    { domain: "com.apple.ActivityMonitor", key: "SortColumn", type: "string", value: "CPUUsage" },
    { domain: "com.apple.dock", key: "expose-animation-duration", type: "float", value: "0.12" }
  ]
}
```

## Example Playbook

    - hosts: all
      roles:
        - { role: feffi.osx-defaults }
