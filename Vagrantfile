# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty32"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible.yml"
  end
end
