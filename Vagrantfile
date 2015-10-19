# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
  config.vm.define "server1" do |s1|
    s1.vm.box = "ubuntu/trusty64"
    s1.vm.network "private_network", ip: "172.20.83.83", auto_config: false #IPs are placeholders to make Vagrant work
    s1.vm.network "private_network", ip: "172.20.84.83", auto_config: false
    s1.vm.provision "shell", inline: <<-SHELL
        #sudo apt-get update
        sudo apt-get install -y vlan ifenslave
        sudo cp /vagrant/server1 /etc/network/interfaces
        sudo modprobe bonding
        sudo modprobe 8021q
        sudo su -c 'echo "8021q" >> /etc/modules'
        sudo su -c 'echo "bonding" >> /etc/modules'
        sleep 10
        sudo ifup -a
    SHELL
  end
  config.vm.define "server2" do |s2|
    s2.vm.box = "ubuntu/trusty64"
    s2.vm.network "private_network", ip: "172.20.83.84", auto_config: false #IPs are placeholders to make Vagrant work
    s2.vm.network "private_network", ip: "172.20.84.84", auto_config: false
    s2.vm.provision "shell", inline: <<-SHELL
        #sudo apt-get update
        sudo apt-get install -y vlan ifenslave
        sudo cp /vagrant/server2 /etc/network/interfaces
        sudo modprobe bonding
        sudo modprobe 8021q
        sudo su -c 'echo "8021q" >> /etc/modules'
        sudo su -c 'echo "bonding" >> /etc/modules'
        sleep 10
        sudo ifup -a
    SHELL
  end
end
