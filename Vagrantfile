# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  # VM config
  config.vm.box = "centos/7"

  config.vm.network :private_network, ip: "192.168.120.2"

  # enable after install httpd
  #config.vm.synced_folder "../webapp", "/var/www/webapp", owner: "apache" ,mount_options: ['dmode=777', 'fmode=666']

  # Network
  # SSH
  config.vm.network "forwarded_port", id: "ssh", guest: 22, host: 2001
  config.vm.network "forwarded_port", guest: 80, host: 8040
  # MySQL server
  #config.vm.network "forwarded_port", guest: 3306, host: 8031

  # VirtualBox config
  config.vm.provider "virtualbox" do |v|
    v.name = "virtual-machine-name"
    v.memory = 512
    v.cpus = 1
  end

  # provisioning
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
  end
end
