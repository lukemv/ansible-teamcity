# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  
  config.vm.define "db" do |db|
    db.vm.box = "centos/7"
    db.vm.network "public_network", ip: "10.10.10.132"
    db.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
   db.vm.provision "shell",
    inline: "curl https://github.com/lukemv.keys >> /home/vagrant/.ssh/authorized_keys"
  end

  config.vm.define "tcserver" do |tcserver|
    tcserver.vm.box = "centos/7"
    tcserver.vm.network "public_network", ip: "10.10.10.133"
    tcserver.vm.provider "virtualbox" do |vb|
      vb.memory = "2096"
    end
    tcserver.vm.provision "shell",
      inline: "curl https://github.com/lukemv.keys >> /home/vagrant/.ssh/authorized_keys"
  end

  config.vm.define "tcagent" do |tcagent|
    tcagent.vm.box = "centos/7"
    tcagent.vm.network "public_network", ip: "10.10.10.134"
    tcagent.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
    tcagent.vm.provision "shell",
      inline: "curl https://github.com/lukemv.keys >> /home/vagrant/.ssh/authorized_keys"
  end

end