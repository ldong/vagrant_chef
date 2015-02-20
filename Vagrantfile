# -*- mode: ruby -*-
# vi: set ft=ruby :

file_location = '~/VMs/src'

Vagrant.configure("2") do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "ubuntu_on_rails"
  config.vm.box_url = 'https://dl.dropboxusercontent.com/s/p5wqxl56ckvw03q/ubuntu12.04_chef_rails4.box'

  config.vm.synced_folder file_location, "/home/vagrant/src"
  config.vm.synced_folder "~", "/vagrant", disabled: true

  config.vm.network :forwarded_port, guest: 8000, host: 9000
  config.vm.network :forwarded_port, guest: 8001, host: 9001
  config.vm.network :forwarded_port, guest: 8080, host: 9080
  config.vm.network :forwarded_port, guest: 8081, host: 9081
  config.vm.network :forwarded_port, guest: 8888, host: 9888
  config.vm.network :forwarded_port, guest: 3000, host: 3000

  # enable X11
  # config.ssh.forward_x11 = true

  config.vm.provider :virtualbox do |vb|
    vb.customize [ "modifyvm", :id, "--memory", 2048 ]
    vb.customize [ "modifyvm", :id, "--natdnshostresolver1", "on" ]
    vb.customize [ "setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-src", "1"]
  end
end
