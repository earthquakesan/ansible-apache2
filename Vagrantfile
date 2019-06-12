# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "box" do |box|
    box.vm.box = "geerlingguy/ubuntu1804"
    box.vm.network "private_network", ip: "192.168.111.111"
    box.vm.hostname = "box.localhost.local"
    box.ssh.private_key_path = File.expand_path('~/.vagrant.d/insecure_private_key')
    box.ssh.insert_key = false

    # Provisioning configuration for Ansible.
    box.vm.provision "ansible" do |ansible|
      ansible.playbook = "main.yml"
    end
  end
  
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end
  
end
