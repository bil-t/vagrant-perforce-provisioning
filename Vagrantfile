Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.port = 2223  
  config.ssh.forward_agent = true
  config.ssh.forward_x11 = true
  config.vm.network "forwarded_port", guest: 1666, host: 1666
  config.vm.network :forwarded_port, guest: 22, host: 2222, id: "ssh", disabled: true
  config.vm.network :forwarded_port, guest: 22, host: 2223, auto_correct: true
  config.vm.provision "shell", path: "vagrant/provision_once.sh"
  config.vm.provision "shell", path: "vagrant/provision_always.sh", run: "always", privileged: "false"
end
