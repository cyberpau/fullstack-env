# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

# CUSTOMIZE PARAMETERS:
IMAGE_NAME = "centos/7"

MASTER_NAME = "master"
MASTER_NUM = 1
MASTER_CPU = 2
MASTER_MEM = 2048

WORKER_NAME = "worker"
WORKER_NUM = 2
WORKER_CPU = 1
WORKER_MEM = 1024

Vagrant.configure("2") do |config|

  ## Provision Master Nodes -------------------------
  (1..MASTERS_NUM).each do |i|      
    config.vm.define "#{MASTERS_NAME}#{i}" do |master|
        master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: "#{IP_BASE}#{i + 99*i}"
        master.vm.hostname = "#{MASTERS_NAME}#{i}"
        master.vm.provider "virtualbox" do |v|
            v.memory = MASTERS_MEM
            v.cpus = MASTERS_CPU
        end
        #config.vm.provision "shell", path: "bootstrap.sh"
        #config.vm.provision "shell", path: "master-bootstrap.sh"
    end
  end

  ## Provision Worker Nodes -------------------------
  (1..NODES_NUM).each do |j|
    config.vm.define "#{WORKER_NAME}#{j}" do |node|
        node.vm.box = IMAGE_NAME
        node.vm.network "private_network", ip: "#{IP_BASE}#{j + 100}"
        node.vm.hostname = "#{WORKER_NAME}#{j}"
        node.vm.provider "virtualbox" do |v|
            v.memory = WORKER_MEM
            v.cpus = WORKER_CPU
        end
        #config.vm.provision "shell", path: "bootstrap.sh"
        #config.vm.provision "shell", path: "worker-bootstrap.sh"
    end
  end


  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = IMAGE_NAME

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
