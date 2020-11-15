$useraddscript = <<SCRIPT
useradd -m henk
groupadd operators
usermod -aG operators henk
mkdir /operators
chown henk /operators
chgrp operators /operators
SCRIPT


Vagrant.configure('2') do |config|

    # Ssh settings
    config.ssh.insert_key = false

    # Default settings
    config.vm.box = "ubuntu/bionic64"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
        vb.cpus = 1
    end

    config.vm.define :web1 do |machine1|
        machine1.vm.host_name = "web1.local"
        machine1.vm.network "private_network", ip: "192.168.10.251"
        machine1.vm.provision "shell", inline: $useraddscript
		machine1.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
    end
	
	config.vm.define :web2 do |machine2|
        machine2.vm.host_name = "web2.local"
        machine2.vm.network "private_network", ip: "192.168.10.252"
        machine2.vm.provision "shell", inline: $useraddscript
		machine2.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
    end

    config.vm.define :proxy do |machine3|
        machine3.vm.host_name = "proxy.local"
        machine3.vm.network "private_network", ip: "192.168.10.254"
        machine3.vm.provision "shell", inline: $useraddscript
		machine3.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
	end
end