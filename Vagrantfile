# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.network "private_network", ip: "10.100.0.3"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4000"
  end
end