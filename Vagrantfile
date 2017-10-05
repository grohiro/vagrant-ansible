# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  # VM config
  config.vm.box = "centos/6"

  config.vm.network :private_network, ip: "192.168.120.2"

  # Shared folders
  config.vm.synced_folder "./", "/vagrant", type: "nfs"

  # Network
  # SSH
  config.vm.network "forwarded_port", id: "ssh", guest: 22, host: 2001
  # www
  config.vm.network "forwarded_port", guest: 80, host: 8040
  # MySQL
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
