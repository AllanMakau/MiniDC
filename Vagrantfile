# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<-SCRIPT

echo instalando python........
sudo apt-get install python-mysqldb
SCRIPT

Vagrant.configure("2") do |config|


   config.vm.box = "ubuntu/bionic64"
   
   config.vm.define "web" do |web|
	   web.vm.box = "ubuntu/bionic64"
	   web.vm.hostname = "blog"
	   web.vm.network "private_network", ip: "172.17.177.22"  
	   
	   web.vm.provider "virtualbox" do |v|
		   v.memory = 512
		   v.cpus = 1
	   end
   end



	

   config.vm.define "db" do |db|
       db.vm.box = "ubuntu/bionic64"
	   db.vm.hostname = "database"
	   db.vm.network "private_network", ip: "172.17.177.21"
	   
	   db.vm.provider "virtualbox" do |v|
		   v.memory = 512
		   v.cpus = 1
	   end
	   #db.vm.provision "shell", inline: $script
   end
 

 
   config.vm.define "ansible" do |ansible|
       ansible.vm.box = "ubuntu/bionic64"
	   ansible.vm.hostname = "ansible"
	   ansible.vm.network "private_network", ip: "172.17.177.11"
	   ansible.vm.synced_folder './','/vagrant',mount_options:["dmode=750,fmode=600"]
	   
	   ansible.vm.provider "virtualbox" do |v|
		   v.memory = 512
		   v.cpus = 1
	   end
	   
	   
	   
	   ansible.vm.provision :ansible_local do |controllerAnsible|
			controllerAnsible.install_mode = "default"
			controllerAnsible.playbook = "playbook.yml"
			controllerAnsible.verbose  = true
			controllerAnsible.install  = true
			controllerAnsible.limit    = "all"
			controllerAnsible.inventory_path = "inventory"	
	   end
	   

	  
   end


end





