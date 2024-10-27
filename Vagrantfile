require_relative './vagrant_plugins/key_authorization'

Vagrant.configure('2') do |config|

  CENTOS_6_BOX_IMAGE = ENV['AW_CENTOS_6_BOX_IMAGE']
  CENTOS_6_HOSTNAME = ENV['AW_CENTOS_6_HOSTNAME']
  CENTOS_7_BOX_IMAGE = ENV['AW_CENTOS_7_BOX_IMAGE']
  CENTOS_7_HOSTNAME = ENV['AW_CENTOS_7_HOSTNAME']
  CENTOS_8_BOX_IMAGE = ENV['AW_CENTOS_8_BOX_IMAGE']
  CENTOS_8_HOSTNAME = ENV['AW_CENTOS_8_HOSTNAME']
  UBUNTU_1804_BOX_IMAGE = ENV['AW_UBUNTU_1804_BOX_IMAGE']
  UBUNTU_1804_HOSTNAME = ENV['AW_UBUNTU_1804_HOSTNAME']
  UBUNTU_2004_BOX_IMAGE = ENV['AW_UBUNTU_2004_BOX_IMAGE']
  UBUNTU_2004_HOSTNAME = ENV['AW_UBUNTU_2004_HOSTNAME']
  UBUNTU_2204_BOX_IMAGE = ENV['AW_UBUNTU_2204_BOX_IMAGE']
  UBUNTU_2204_HOSTNAME = ENV['AW_UBUNTU_2204_HOSTNAME']
  WINDOWS_SERVER_2022_BOX_IMAGE = ENV['AW_WINDOWS_SERVER_2022_BOX_IMAGE']
  WINDOWS_SERVER_2022_HOSTNAME = ENV['AW_WINDOWS_SERVER_2022_HOSTNAME']
  
  CPUS = ENV['AW_VM_CPUS']
  MEMORY = ENV['AW_VM_MEMORY']

  authorize_key_for_root config, ENV['AW_SSH_PUBLIC_KEY_PATH']

  config.vm.provider "libvirt"
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = false
  config.vagrant.plugins = [
    'vagrant-hostmanager',
    'vagrant-libvirt',
  ]

  config.vm.define "#{CENTOS_6_HOSTNAME}" do |host|
    host.vm.box = CENTOS_6_BOX_IMAGE
    host.vm.network 'private_network', type: 'dhcp'
    host.vm.hostname = "#{CENTOS_6_HOSTNAME}.vagrant"
  end

  config.vm.define "#{CENTOS_7_HOSTNAME}" do |host|
    host.vm.box = CENTOS_7_BOX_IMAGE
    host.vm.network 'private_network', type: 'dhcp'
    host.vm.hostname = "#{CENTOS_7_HOSTNAME}.vagrant"
  end

  config.vm.define "#{CENTOS_8_HOSTNAME}" do |host|
    host.vm.box = CENTOS_8_BOX_IMAGE
    host.vm.network 'private_network', type: 'dhcp'
    host.vm.hostname = "#{CENTOS_8_HOSTNAME}.vagrant"
  end

  config.vm.define "#{UBUNTU_1804_HOSTNAME}" do |host|
    host.vm.box = UBUNTU_1804_BOX_IMAGE
    host.vm.network 'private_network', type: 'dhcp'
    host.vm.hostname = "#{UBUNTU_1804_HOSTNAME}.vagrant"
  end

  config.vm.define "#{UBUNTU_2004_HOSTNAME}" do |host|
    host.vm.box = UBUNTU_2004_BOX_IMAGE
    host.vm.network 'private_network', type: 'dhcp'
    host.vm.hostname = "#{UBUNTU_2004_HOSTNAME}.vagrant"
  end

  config.vm.define "#{UBUNTU_2204_HOSTNAME}" do |host|
    host.vm.box = UBUNTU_2204_BOX_IMAGE
    host.vm.network 'private_network', type: 'dhcp'
    host.vm.hostname = "#{UBUNTU_2204_HOSTNAME}.vagrant"
  end

  config.vm.define "#{WINDOWS_SERVER_2022_HOSTNAME}" do |host|
    host.vm.box = WINDOWS_SERVER_2022_BOX_IMAGE
    host.vm.network 'private_network', type: 'dhcp'
    host.vm.hostname = "#{WINDOWS_SERVER_2022_HOSTNAME}"
  end

  config.vm.provider :libvirt do |vm|
    vm.cpus = CPUS
    vm.memory = MEMORY
  end

  config.vm.provider :virtualbox do |vm|
    vm.customize ["modifyvm", :id, "--memory", MEMORY]
    vm.customize ["modifyvm", :id, "--cpus", CPUS]
  end

end
