Proving Ground
==============

Vagrant test environment with prepared scenarios.

Getting started
---------------

### Select environment

Environments are seperated in different directories which are self contained with the exception of plugins/custom extensions for vagrant.

```
cd <directory>
```

### Start environment

```
vagrant up
```

### Destroy environment

```
vagrant destroy -f
```

### Update environment

```
vagrant box update
```

### Cleanup environment

```
vagrant box prune
```

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

Ensures the users public key is situated on every virtual machine. This way a passwordless login is possible.gg

### Ansible Provisioning

New roles need to be added from within the `.ansible` directory with the command:

```
ansible-galaxy install <author.role>
```

## License

MIT

