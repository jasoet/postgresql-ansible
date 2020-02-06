# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.define "master" do |master|
    master.vm.network "private_network", ip: "192.168.33.10"
    master.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/postgresql-master/g' /etc/hosts"
    master.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/postgresql-master/g' /etc/hostname"
    master.vm.provision "shell", inline: "sudo reboot"
  end

  config.vm.define "minio" do |slave|
    slave.vm.network "private_network", ip: "192.168.33.11"
    slave.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/minio/g' /etc/hosts"
    slave.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/minio/g' /etc/hostname"
    slave.vm.provision "shell", inline: "sudo reboot"
  end

  config.vm.define "slave-one" do |slave|
    slave.vm.network "private_network", ip: "192.168.33.12"
    slave.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/postgresql-slave-one/g' /etc/hosts"
    slave.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/postgresql-slave-one/g' /etc/hostname"
    slave.vm.provision "shell", inline: "sudo reboot"
  end

  config.vm.define "slave-two" do |slave|
    slave.vm.network "private_network", ip: "192.168.33.13"
    slave.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/postgresql-slave-two/g' /etc/hosts"
    slave.vm.provision "shell", inline: "sudo sed -i 's/ubuntu-bionic/postgresql-slave-to/g' /etc/hostname"
    slave.vm.provision "shell", inline: "sudo reboot"
  end

end
