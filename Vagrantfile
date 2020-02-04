# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.define "master" do |master|
    master.ssh.forward_agent = true
    master.vm.network "private_network", ip: "192.168.33.10"
    master.vm.hostname = "postgresql-master"
  end

  config.vm.define "slave" do |slave|
    slave.ssh.forward_agent = true
    slave.vm.network "private_network", ip: "192.168.33.11"
    slave.vm.hostname = "postgresql-slave"
  end
end
