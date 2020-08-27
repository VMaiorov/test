Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.box_check_update = false
  config.vm.hostname = "test"
  config.vm.network "forwarded_port", guest: 80, host: 8880
  config.vm.network "forwarded_port", guest: 5000, host: 5555
  config.vm.network "public_network", bridge: "wlp0s20f3"
  config.vm.define "test"  
  config.vm.provider "virtualbox" do |vb|
     vb.gui = false
     vb.memory = "2048"
  end
  config.vm.provision "ansible" do |ansible|
    ansible.galaxy_role_file = 'requirements.yml'
    ansible.playbook = "playbook.yml"
  end

end