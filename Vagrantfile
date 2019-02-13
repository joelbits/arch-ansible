Vagrant.configure("2") do |config|
  config.vm.box = "archlinux/archlinux"  
  config.vm.network :private_network, ip: "192.168.50.2"

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end
  # Configure Ansible provisionner
  config.vm.provision :ansible do |ansible|
     ansible.host_key_checking = false
     ansible.inventory_path = "vagrant.inventory"
     ansible.extra_vars = { ansible_python_interpreter: "/usr/bin/python2" }
     ansible.verbose = "extra"
     ansible.playbook = "ansible/install.yml"
  end
end