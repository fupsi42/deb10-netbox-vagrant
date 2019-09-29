# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/buster64"
  config.vm.hostname = "deb10-netbox-demo"

  config.vm.network :forwarded_port, guest: 80, host: 8080, id: 'http'

  config.vm.synced_folder "./config_files", "/vagrant"

#Update VM resources below as needed
  config.vm.provider :virtualbox do |vb|
    vb.name = "Deb10-Netbox-Demo"
    vb.memory = 2048
    vb.cpus = 1
    vb.customize ["modifyvm", :id, "--ostype", "Debian_64"]
  end

  config.vm.provision :shell, path: "bootstrap.sh"

end
