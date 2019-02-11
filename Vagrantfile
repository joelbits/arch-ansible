Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox"
    config.vm.box = "ubuntu/bionic64" 
  
    config.vm.define "server1" do |server1|
      # restrict scope of ansible provisioner to server1 by invoking on its class method off the constructor
      server1.vm.provision :ansible do |ansible|
        ansible.become = true
        ansible.playbook = "ansible-arch-linux-playbook/install.yml"
      end
    end
end