# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # Use a Ubuntu box
  config.vm.box = "phusion/ubuntu-14.04-amd64"

  # Disable automatic box update checking
  # config.vm.box_check_update = false

  # Create a forwarded port mapping for Docker
  config.vm.network "forwarded_port", guest: 2375, host: 2375

  # Create a private network so we can easily talk to the machine
  config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
     # Display the VirtualBox GUI when booting the machine
     vb.gui = false
  
     # Customize the amount of memory on the VM:
     vb.memory = 8096

     # Customize the amount of CPUs on the VM:
     vb.cpus = 4
    
     # Give this a name to make it easier to see
     vb.name = "Ubuntu14.04-Docker"

  end
  
  # Provision with Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/ansible/playbook.yml"
  end

end
