# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.

  config.vm.define :shop do |shop|
    shop.vm.box = "centos64-64"
    shop.vm.network :private_network, ip: "192.168.0.103"
    shop.vm.network :forwarded_port, guest: 22, host: 2202
    shop.vm.hostname = "shop"
  end

  config.vm.define :acct do |acct|
    acct.vm.box = "centos64-64"
    acct.vm.network :private_network, ip: "192.168.0.102"
    acct.vm.network :forwarded_port, guest: 22, host: 2203
    acct.vm.hostname = "acct"
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_file = "ansible-hosts"
    ansible.sudo = true
  end


end
