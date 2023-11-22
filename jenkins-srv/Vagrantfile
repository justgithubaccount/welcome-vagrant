# Multi-Machine

# https://developer.hashicorp.com/vagrant/docs/multi-machine

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "debian/bookworm64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.hostname = "jenkins"

  config.vm.network "private_network", ip: "192.168.56.10"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.cpus = 2
    vb.memory = "2048"
  end

  config.vm.provision "shell" do |shell|
    shell.path = "provisioning/jenkins.sh"
  end
end 