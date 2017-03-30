# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |v|
    v.gui = false
    v.name = "Hadoop tutorial"
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.memory = 1024
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/vagrant.yml"
    ansible.inventory_path = "ansible/inventory/vagrant/hosts"
    ansible.limit = 'all'
    ansible.verbose = 'vvvv'
  end
end
