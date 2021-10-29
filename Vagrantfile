# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "peru/ubuntu-20.04-server-amd64"
    # config.vm.network "private_network", ip: "192.168.33.70"
    config.vm.hostname = "sreeram"
    # config.vm.network :forwarded_port, host: 1122, guest: 1122

    config.vm.provider "virtualbox" do |v|
        v.gui = false
        v.memory = 624
        v.linked_clone = true
      end
    config.ssh.insert_key = false
#    config.vm.synced_folder "/home/filius-fall/ancible_test", "/home/vagrant/ancible_test"

    # config.vm.provision "ansible" do |ansible|
    #     ansible.playbook = "playbook.yml"
    # end

    config.vm.define "app1" do |app|
        app.vm.hostname = "orc-app1.test"
        app.vm.network :private_network, ip: "192.168.33.10"
    end   
    
    config.vm.define "app2" do |app|
        app.vm.hostname = "orc-app2.test"
        app.vm.network :private_network, ip: "192.168.33.20"
    end

    config.vm.define "db" do |db|
        db.vm.hostname = "orc-db.test"
        db.vm.network :private_network, ip: "192.168.33.30"
    end 
end

