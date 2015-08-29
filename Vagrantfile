# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
config.vm.box = "centOS65Box"
config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"
config.vm.network "forwarded_port", guest: 3000, host: 3000
config.vm.network "private_network", ip: "192.168.33.15"
##　ローカルとリモートをデータ共有する
# config.vm.synced_folder "/Users/NAGAISHI/Devenv/ruby-tutorial-ansible/host_data", "/home/vagrant/remote_data"

config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./ansible/dev.yml"
#        ansible.playbook = "provision_vagrant.yml"  # 作成したplaybookファイル名
#        ansible.inventory_path = "hosts"  # 作成したインベントリーファイル名
  end
end
