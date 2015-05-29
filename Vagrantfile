# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.insert_key = false

  config.vm.define :web1 do |node|
    node.vm.hostname = "web1"
    node.vm.box = "centos"
    node.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"

    node.vm.network :private_network, ip: "192.168.33.11"
    node.vm.network :forwarded_port, guest: 80, host: 8080
    node.vm.network :forwarded_port, guest: 9200, host: 9200
    node.vm.network :forwarded_port, guest: 22, host: 2003
  end

  config.vm.define :web2 do |node|
    node.vm.hostname = "web2"
    node.vm.box = "centos"
    node.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"

    node.vm.network :private_network, ip: "192.168.33.12"
    node.vm.network :forwarded_port, guest: 80, host: 8081
    node.vm.network :forwarded_port, guest: 9200, host: 9201
    node.vm.network :forwarded_port, guest: 22, host: 2004
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "512"]
  end
end
