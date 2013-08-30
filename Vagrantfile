# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos-6.4"
  config.vm.box_url = "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20130427.box"

  config.vm.network :forwarded_port, guest: 80, host: 8080
  config.vm.network :private_network, ip: "10.0.0.101"

  config.vm.provision :ansible do |ansible|
    ansible.playbook       = 'provisioning/site.yml'
    ansible.inventory_file = 'provisioning/ansible_hosts'
    ansible.sudo           = true
    ansible.verbose        = true
  end
end
