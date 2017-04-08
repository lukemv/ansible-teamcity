# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.define "db" do |db|
    db.vm.box = "centos/7"
    db.vm.network "public_network", ip: "10.10.10.132"
    db.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
  end

  config.define "tcserver" do |tcserver|
    tcserver.vm.box = "centos/7"
    tcserver.vm.network "public_network", ip: "10.10.10.133"
    tcserver.vm.provider "virtualbox" do |vb|
      vb.memory = "2096"
    end
  end
end