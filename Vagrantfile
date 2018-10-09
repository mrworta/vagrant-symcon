# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "forwarded_port", guest: 3777, host: 3777
  config.vm.provider "virtualbox" do |vb|
     vb.memory = "4096"
  end
  
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update 
	apt-get upgrade -y
	apt-get install -y wget
    echo "deb [arch=amd64] http://apt.symcon.de/ stable ubuntu" > /etc/apt/sources.list.d/symcon.list
	wget -qO - http://apt.symcon.de/symcon.key | sudo apt-key add -
    apt-get update
    apt-get install -y symcon
  SHELL
end
