# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "base"

  config.vm.box = "ubuntu/bionic64"

 
  config.vm.define "DNSA" do |dns_a|
    dns_a.vm.hostname = "DNSA"
    dns_a.vm.network "private_network", ip: "192.168.57.10" 
    dns_a.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y bind9
      
    SHELL
  end

 
  config.vm.define "DNSB" do |dns_b|
    dns_b.vm.hostname = "DNSB"
    dns_b.vm.network "private_network", ip: "192.168.57.20" 
    dns_b.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y bind9
     
    SHELL
  end

  config.vm.define "CLIENTE" do |cliente|
    cliente.vm.hostname = "CLIENTE"
    cliente.vm.network "private_network", ip: "192.168.57.30"
    cliente.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y bind9 dnsutils
      echo "nameserver 192.168.57.10" >> /etc/resolv.conf
      echo "nameserver 192.168.57.20" >> /etc/resolv.conf
    SHELL
  end

end
