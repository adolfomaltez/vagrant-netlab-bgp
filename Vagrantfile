# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/site.yaml"
    ansible.inventory_path = "ansible/inventory.ini"
    ansible.verbose = false
    ansible.limit = "all"
  end

end
