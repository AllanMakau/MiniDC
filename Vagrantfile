# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
   
   
   config.vm.define "web" do |web|
    web.vm.box = "MiniDC-Blog"
	config.vm.network "private_network", ip: "172.17.177.22"

   end

   config.vm.define "db" do |db|
    db.vm.box = "MiniDC-Database"
	config.vm.network "private_network", ip: "172.17.177.21"
   end
  
   config.vm.define "ansible" do |ansible|
    ansible.vm.box = "MiniDC-AnsibleController"
	config.vm.network "private_network", ip: "172.17.177.11"
   end

end





