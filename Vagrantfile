require_relative './plugins/key_authorization'

Vagrant.configure('2') do |config|

  # [general]
  authorize_key_for_root config, '~/.ssh/id_rsa.pub'
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = false

  # [CentOS 7]
  {
    'centos-7' => '192.168.33.11',
  }.each do |short_name, ip|
    config.vm.define short_name do |host|
      host.vm.box = 'centos/7'
      host.vm.network 'private_network', ip: ip
      host.vm.hostname = "#{short_name}.vagrant"
      host.hostmanager.aliases = "#{short_name}"
    end
  end

  # [Debian 8]
  {
    'debian-jessie' => '192.168.33.12',
  }.each do |short_name, ip|
    config.vm.define short_name do |host|
      host.vm.box = 'debian/jessie64'
      host.vm.network 'private_network', ip: ip
      host.vm.hostname = "#{short_name}.vagrant"
      host.hostmanager.aliases = "#{short_name}"
    end
  end

  # [Ubuntu 16.04]
  {
    'ubuntu-xenial' => '192.168.33.13',
  }.each do |short_name, ip|
    config.vm.define short_name do |host|
      host.vm.box = 'bento/ubuntu-16.04'
      host.vm.network 'private_network', ip: ip
      host.vm.hostname = "#{short_name}.vagrant"
      host.hostmanager.aliases = "#{short_name}"
    end
  end

end
