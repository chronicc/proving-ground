Proving Ground
==============

Vagrant test environment for automation and applications/scripts.

## Environment Control

### Create environment

    $ vagrant up

### Destroy environment

    $ vagrant destroy -f

### Update environment

    $ vagrant box update
    $ vagrant box prune

## Features

### Hostmanager

Manages `/etc/hosts` file of the system to ensure virtual machines are reachable by <short-name>.vagrant. To ensure every user in sudo group can update `/etc/hosts` the sudoers file needs to be modified:

```
# vagrant-hostmanager
Cmnd_Alias VAGRANT_HOSTMANAGER_UPDATE = /bin/cp */.vagrant.d/tmp/hosts.local /etc/hosts
%sudo ALL=(root) NOPASSWD: VAGRANT_HOSTMANAGER_UPDATE
```

This of course can also be specific to one user instead of `%sudo`.

### SSH key integration

Plugin: `plugins/key_authorization.rb`

Ensures the users public key is situated on every virtual machine. This way a passwordless login is possible.

## License

MIT
