Proving Ground
==============

Vagrant test environment with prepared scenarios.

## Getting started

### Prepare workstation

1. Install vagrant. You can download the latest version [here](https://www.vagrantup.com/downloads.html).
1. Install virtualbox (support will be reduced subsequently) and libvirt including dev dependencies (e.g. libvirt-dev on debian distributions).
1. Install vagrant plugins.
    ```
    vagrant plugin install vagrant-hosts
    vagrant plugin install vagrant-hostmanager
    vagrant plugin install vagrant-libvirt
    vagrant plugin install vagrant-mutate
    vagrant plugin install vagrant-share
    ```

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

### Stop environment

```
vagrant halt
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

If a machine was not added to the hosts file after being created, run `vagrant hostmanager` manually. Sometimes this fixes the problem.

### SSH key integration

Plugin: `plugins/key_authorization.rb`

Ensures the users public key is situated on every virtual machine. This way a passwordless login is possible.

### Ansible Provisioning

New roles need to be added from within the `.ansible` directory with the command:

```
ansible-galaxy install <author.role>
```

## License

MIT

