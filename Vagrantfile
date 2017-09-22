
Vagrant.configure("2") do |config|
  config.vm.hostname = "rails-app-template"
  config.vm.box = "CentOS7.1"
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-7.1_chef-provisionerless.box"

  config.vm.network "forwarded_port", guest: 3000, host: 4002

  config.vm.network "private_network", ip: "192.168.33.12"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/site.yml"
    ansible.inventory_path = "ansible/hosts/vagrant/inventory"
    ansible.limit = 'vagrant'
    ansible.config_file = "ansible/ansible.cfg"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

end
