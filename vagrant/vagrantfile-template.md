# -*- mode: ruby -*-
# vi: set ft=ruby tabstop=2

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    v.customize ["modifyvm", :id, "--memory", "256"]
  end
end
