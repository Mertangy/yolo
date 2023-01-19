# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = "geerlingguy/ubuntu2004"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.linked_clone = true
  end

  # Application server 1.
  config.vm.define "frontend" do |app|
    app.vm.hostname = "front-end"
    app.vm.network :private_network, ip: "192.168.60.3"
  end

  # Application server 2.
  config.vm.define "backend" do |app|
    app.vm.hostname = "nodejs-backend"
    app.vm.network :private_network, ip: "192.168.60.4"
  end

  # Database server.
  config.vm.define "database" do |db|
     db.vm.hostname = "mongo-db"
    db.vm.network :private_network, ip: "192.168.60.5"
  end
end