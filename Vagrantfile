Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false
  config.vm.hostname = "test"
  config.vm.network "private_network", ip 127.0.0.1
  
  config.vm.define "test"  
  config.vm.provider "virtualbox" do |vb|
     vb.gui = false
     vb.memory = "2048"
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end