#one centos box: https://linuxacademy.com/blog/linux/vagrant-cheat-sheet-get-started-with-vagrant/

Vagrant.configure(2) do | config |

		config.vm.box = "centos/7"
		config.vm.hostname = "webserver01"
		config.vm.network :private_network , ip: "192.168.88.10"

		config.vm.provider "virtualbox" do | vb |
			vb.memory = "1024"
			vb.cpus = "2"
		end	

		config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"

		config.vm.provision "ansible" do | ansible |
				ansible.verbose = "y"
				ansible.playbook = "webserver.yml"
		end
	  	
end