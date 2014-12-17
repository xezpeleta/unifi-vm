# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "xezpeleta/wheezy64"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 8443, host: 8443
  config.vm.network "private_network", ip: "192.168.33.12"
  config.vm.network "public_network"

  config.vm.provider "virtualbox" do |vb|
     vb.gui = false
     vb.name = "unifi"
     vb.customize ["modifyvm", :id, "--memory", "512"]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/hosts-vagrant"
    ansible.limit = 'all'
    ansible.host_key_checking = false
    ansible.verbose = false
  end

end
