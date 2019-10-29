# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|


   config.vm.box = "ubuntu/bionic64"
   
   config.vm.define "web" do |web|
	   web.vm.box = "ubuntu/bionic64"
	   web.vm.hostname = "blog"
	   web.vm.network "private_network", ip: "172.17.177.22"
	   config.vm.provider "virtualbox" do |v|
		   v.name = "ubuntu"
		   v.memory = 1024
		   v.cpus = 2
	   end
	   
   end



	
   config.vm.define "db" do |db|
       db.vm.box = "ubuntu/bionic64"
	   db.vm.hostname = "database"
	   db.vm.network "private_network", ip: "172.17.177.21"
	   config.vm.provider "virtualbox" do |v|
		   v.name = "ubuntu"
		   v.memory = 1024
		   v.cpus = 2
	   end
   end

   

  
   config.vm.define "ansible" do |ansible|
       ansible.vm.box = "ubuntu/bionic64"
	   ansible.vm.hostname = "ansible"
	   ansible.vm.network "private_network", ip: "172.17.177.11"
	   config.vm.provider "virtualbox" do |v|
		   v.name = "ubuntu"
		   v.memory = 1024
		   v.cpus = 2
	   end
   end

end





