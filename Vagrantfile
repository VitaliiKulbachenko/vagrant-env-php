# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
	# имя в `vagrant global-status`
	config.vm.define "centos7-lamp-httpd" do |t|
	end

	config.vm.box = "VitaliiKulbachenko/centos7-lamp-httpd"
	config.vm.box_version = "1"
	#config.ssh.username = "vagrant"
	#config.ssh.password = "vagrant"
	config.vm.hostname = "default.dev"
	config.vm.network :forwarded_port, host: 80, guest: 80
	config.vm.network :forwarded_port, host: 443, guest: 443
	config.vm.network :forwarded_port, host: 3306, guest: 3306
    config.vm.network "private_network", ip: "192.168.33.11"
    config.vm.synced_folder "./www", "/var/www", type: "virtualbox", :mount_options => ["dmode=777", "fmode=666"]
    config.vm.synced_folder "./sharing", "/home/vagrant/sharing", type: "virtualbox", :mount_options => ["dmode=777", "fmode=666"]
    
    # Настройка  VirtualBox
	config.vm.provider "virtualbox" do |v|
	v.name = "centos7-lamp-httpd" 
	v.memory = 1024
	v.cpus = 1
	end   

 	#config.vm.provision "ansible" do |ansible|
    #    ansible.playbook = "ansible/playbook.yml"
    #    ansible.sudo = true
    #    #ansible.inventory_path = "playbooks"
    #end


	config.vm.provision :shell, inline: "echo Good job, now enjoy your new vbox: http://192.168.33.11"
end
 
