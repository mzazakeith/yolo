# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/ubuntu2004"

  config.vm.network "forwarded_port", guest: 3002, host: 3002, protocol: "tcp"
  config.vm.network "forwarded_port", guest: 5000, host: 5000, protocol: "tcp"

  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.memory = 2048
  end

  # Ansible provisioning.
  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.verbose = "vv"
    ansible.config_file = "ansible.cfg"
    ansible.playbook = "playbook.yml"
  end
end
