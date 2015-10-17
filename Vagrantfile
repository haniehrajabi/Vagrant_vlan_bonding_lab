# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
  config.vm.define "server1" do |s1|
    s1.vm.box = "ubuntu/trusty64"
    s1.vm.network "private_network", ip: "172.20.83.83", auto_config: false #IPs are placeholders to make Vagrant work
    s1.vm.network "private_network", ip: "172.20.84.83", auto_config: false
  end
  config.vm.define "server2" do |s2|
    s2.vm.box = "ubuntu/trusty64"
    s2.vm.network "private_network", ip: "172.20.83.84", auto_config: false #IPs are placeholders to make Vagrant work
    s2.vm.network "private_network", ip: "172.20.84.84", auto_config: false
  end
end
