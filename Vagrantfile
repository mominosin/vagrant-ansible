# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"


$script = <<SCRIPT
sudo apt-get install python-setuptools
sudo easy_install pip
sudo pip install ansible -U
cd /vagrant
ansible-playbook -i hosts vagrant-playbook.yml
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "Ubuntu14.04"
  config.vm.network "private_network", ip: "192.168.56.13"
  config.vm.synced_folder "./", "/vagrant" ,mount_options: ["dmode=777","fmode=666"]
  config.vm.synced_folder "C:/Users/shingo.suzuki/work", "/vagrant_dir" ,mount_options: ["dmode=777","fmode=666"]

  config.vm.provider "virtualbox" do |vb|
     vb.customize ["modifyvm", :id, "--memory", "1024"]
  end
 
  config.vm.provision :shell, :inline => $script

end
