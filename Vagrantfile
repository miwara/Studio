# coding: utf-8
Vagrant.configure("2") do |config|
  config.vm.define "centos" do |node|
    node.vm.box = "bento/centos-7.2"
    node.vm.hostname = "centos"
    node.vm.network "forwarded_port", guest: 80, host: 8080
    node.vm.network "private_network", ip: "192.168.33.10"

    node.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end

  config.vm.define "archlinux" do |node|
    node.vm.box = "miwara/archlinux"
    node.vm.hostname = "archlinux"
    node.vm.network "forwarded_port", guest: 80, host: 8081
    node.vm.network "private_network", ip: "192.168.33.11"
  end
end
