# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = "2"
    vb.memory = "2048"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y build-essential python-dev python-setuptools
    easy_install pip
    pip install ansible
    ansible-playbook -c local -i 'localhost,' /vagrant/mysql57.yml
  SHELL
end
