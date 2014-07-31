# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

	config.vm.define "phonegapbox", primary: true do |m|
		m.vm.box = "hashicorp/precise32"
		m.vm.network "private_network", type: "dhcp"
		m.ssh.forward_agent = true
		m.ssh.forward_x11 = true
		
	end

	config.vm.define "gingerbread", autostart: false do |m|
		m.vm.box = "android2.3"
		m.vm.boot_timeout = 1
		m.vm.network "private_network", type: "dhcp"
		m.vm.provider :virtualbox do |vb|
			vb.gui = true
			vb.memory = 256
			vb.cpus = 1
		end
	end

end
