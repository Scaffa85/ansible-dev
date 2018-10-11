# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  ## Setup Ansible Server
  config.vm.define "acs" do |acs|
    acs.vm.box = "ubuntu/xenial64"
    acs.vm.hostname = "acs"
    acs.vm.network "private_network", ip: "192.168.33.10"
  end

  ## Setup Web Server
  config.vm.define "ubuntu" do |web|
    web.vm.box = "ubuntu/xenial64"
    web.vm.hostname = "ubuntu"
    web.vm.network "private_network", ip: "192.168.33.20"
    web.vm.network "forwarded_port", guest: 80, host: 8080
  end

  ## Setup Database Server
  config.vm.define "centos" do |db|
    db.vm.box = "centos/7"
    db.vm.hostname = "centos"
    db.vm.network "private_network", ip: "192.168.33.30"
  end

end
