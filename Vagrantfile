# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
      config.vm.define "node1" do |config|

      config.vm.hostname = "cassandra-node-1"
      config.vm.box = "hashicorp/precise64"
      config.vm.network :private_network, ip: "192.168.56.101"

      config.vm.provision "ansible" do |ansible|
        ansible.playbook = "provisioning/playbook.yml"
      end

      config.vm.provider :virtualbox do |vb|
        vb.name = "cassandra-node-1"
        vb.customize ["modifyvm", :id, "--memory", 1024]
        vb.customize ["modifyvm", :id, "--cpus", 2]
      end

    end
end
