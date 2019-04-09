pocd_node = { 
	:host => "cm571-template", 
	:box => "centos/7", 
	:repository => "D:/Tutorials/",
	:ram => 2048,
	:cpu => 2,
	:gui => false 
}

Vagrant.configure("2") do |config|
	config.vm.define pocd_node[:host] do |pocd_config|
		pocd_config.vm.box = pocd_node[:box]
		pocd_config.vm.network "public_network"
		pocd_config.vm.provider :virtualbox do |v|
			v.name = pocd_node[:host].to_s
			v.gui = pocd_node[:gui]
			v.customize ["modifyvm", :id, "--memory", pocd_node[:ram].to_s]
			v.customize ["modifyvm", :id, "--cpus", pocd_node[:cpu].to_s]
		end
		
		#pocd_config.vm.synced_folder pocd_node[:repository], "/repository",
		#	id: "repository",
		#	owner: "vagrant",
		#	group: "vagrant"
	end
end