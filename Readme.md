```
vagrant box add Ubuntu14.04 https://cloud-images.ubuntu.com/vagrant/trusty/20140716/trusty-server-cloudimg-amd64-vagrant-disk1.box
vagrant provision
```
Vagrantfile の中で```ansible-playbook -i hosts vagrant-playbook.yml```を実行している。

