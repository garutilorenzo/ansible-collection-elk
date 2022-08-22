# -*- mode: ruby -*-
# vi: set ft=ruby :

NNODES=6

$script = <<-SCRIPT
echo "<CHANGE_ME>" >> /home/vagrant/.ssh/authorized_keys
SCRIPT

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  (0..NNODES - 1).each do |i|
    config.vm.define "k8s-ubuntu-#{i}" do |node|
      #node.vm.box = "ubuntu/focal64"
      node.vm.box = "ubuntu/jammy64"
      node.vm.hostname = "k8s-ubuntu-#{i}"
      config.vm.provider "virtualbox" do |v|
          v.memory = 2048
          v.cpus = 2
      end
      node.vm.network "private_network", ip: "192.168.25.11#{i}"
      node.vm.provision "shell", inline: $script
      node.vm.provision "shell", inline: "echo hello from node #{i}"
    end
  end
end