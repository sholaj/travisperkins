# Defines our Vagrant environment
#
# -*- mode: ruby -*-
# vi: set ft=ruby :



Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.forward_agent = true


    # create server
  config.vm.define :travisperkins do |travisperkins|
    travisperkins.vm.hostname = "travisperkins"
    travisperkins.vm.network :private_network, ip: "10.0.15.100"
    travisperkins.vm.provider "virtualbox" do |vb|
          vb.memory = "1024"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook       = "playbook.yml"
    ansible.inventory_path = "ansible/inventory/vagrant"
    ansible.verbose        = true
  end

  end
  
end

