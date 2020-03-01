# Alpine Desktop VM

Create a Alpine Linux Desktop VM with VirtualBox by using Packer.

- Display Manager : LXDM
- Desktop Environment : MATE
- Alpine : https://alpinelinux.org/

## Usage
Install [Packer], [Vagrant] and [VirtualBox].

- https://www.packer.io/downloads.html
- https://www.vagrantup.com/downloads.html
- https://www.virtualbox.org/wiki/Downloads

### Versions
- Packer ![version](https://img.shields.io/badge/version-1.5.4-blue)
- Vagrant ![version](https://img.shields.io/badge/version-2.2.7-blue)
- Virtualbox ![version](https://img.shields.io/badge/version-5.2.34-blue)
- Alpine Linux ![version](https://img.shields.io/badge/version-3.11.3-blue)

## Build box
```packer build mategui.json```

## Launch VM

```vagrant up```

Autologin on startup


## Credentials
- User : vagrant
- Pass : vagrant
- Keyboard : qwerty

