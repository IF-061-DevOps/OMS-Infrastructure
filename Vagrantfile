# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure(2) do |config|

  config.vm.provision "shell", :inline => "sudo cp /home/devops/OMS-Infrastructure/hosts /etc/hosts", run: "always"
  config.vm.provision "shell", :inline => "sudo ip link set eth1 mtu 1462", run: "always"
  config.vm.provision "shell", :inline => "sudo ip link set eth0 mtu 1462", run: "always"
    config.vm.synced_folder '.','/vagrant', disabled: true
config.vm.synced_folder '.', '/home/vagrant/sync', disabled: true
  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant"
config.vm.boot_timeout = 30
config.vm.provider "virtualbox" do |v|
  v.memory = "1024"
  v.cpus = 2
end
  config.vm.box = "basehost"
  config.ssh.forward_agent = true
  config.ssh.private_key_path = "~/.ssh/id_rsa"

  config.vm.define "ansible" do |ansible|
    ansible.vm.hostname = "ansible.devops.local"
    ansible.vm.network "public_network", bridge: "oms0", :mac => "080027844491", :adapter => 1 
    ansible.vm.provision "shell", inline: <<-SHELL
      sudo yum install epel-release -y
      sudo yum install PyYAML python-httplib2 python-jinja2 python-keyczar python-paramiko python-setuptools python-six sshpass -y
      sudo yum install ansible.rpm http://releases.ansible.com/ansible-network/2.0.1.0-0.2/ansible-2.0.1.0-0.2.network.el7.centos.noarch.rpm -y
SHELL
    ansible.ssh.forward_agent = true
  end

  config.vm.define "balancer" do |balancer|
    balancer.vm.hostname = "balancer"
#   balancer.vm.network "private_network", ip: "192.168.22.11"
    balancer.vm.network "public_network", bridge: "oms0", :mac => "080027844492", :adapter => 1
  end

  config.vm.define "jenkins" do |jenkins|
    jenkins.vm.hostname = "jenkins"
#    jenkins.vm.network "private_network", ip: "192.168.22.12"
    jenkins.vm.network "public_network", bridge: "oms0", :mac => "080027844493", :adapter => 1
    jenkins.ssh.forward_agent = true
  end

  config.vm.define "zabbix" do |zabbix|
    zabbix.vm.hostname = "zabbix"
#   zabbix.vm.network "private_network", ip: "192.168.22.13"
    zabbix.vm.network "public_network", bridge: "oms0", :mac => "080027844494", :adapter => 1
    zabbix.ssh.forward_agent = true
  end

  config.vm.define "repo" do |repo|
    repo.vm.hostname = "repo"
#   repo.vm.network "private_network", ip: "192.168.22.14"
    repo.vm.network "public_network", bridge: "oms0", :mac => "080027844495", :adapter => 1
    repo.ssh.forward_agent = true
  end

  config.vm.define "logs" do |logs|
    logs.vm.hostname = "logs"
#    logs.vm.network "private_network", ip: "192.168.22.15", :adapter => 1
    logs.vm.network "public_network", bridge: "oms0", :mac => "080027844496", :adapter => 1
    logs.ssh.forward_agent = true
  end

  config.vm.define "web1" do |web1|
     web1.vm.hostname = "web1"
#    web1.vm.network "private_network", ip: "192.168.22.21", :adapter => 1
    web1.vm.network "public_network", bridge: "oms0", :mac => "080027844497", :adapter => 1
    web1.ssh.forward_agent = true
  end

  config.vm.define "web2" do |web2|
    web2.vm.hostname = "web2"
#    web2.vm.network "private_network", ip: "192.168.22.22"
    web2.vm.network "public_network", bridge: "oms0", :mac => "080027844498", :adapter => 1
    web2.ssh.forward_agent = true
  end

  config.vm.define "web3" do |web3|
    web3.vm.hostname = "web3"
#    web3.vm.network "private_network", ip: "192.168.22.23"
    web3.vm.network "public_network", bridge: "oms0", :mac => "080027844499", :adapter => 1
    web3.ssh.forward_agent = true
  end

  config.vm.define "db1" do |db1|
    db1.vm.hostname = "db1"
#    db1.vm.network "private_network", ip: "192.168.22.31"
    db1.vm.network "public_network", bridge: "oms0", :mac => "08002784449a", :adapter => 1
    db1.ssh.forward_agent = true
  end

  config.vm.define "db2" do |db2|
    db2.vm.hostname = "db2"
#    db2.vm.network "private_network", ip: "192.168.22.32"
    db2.vm.network "public_network", bridge: "oms0", :mac => "08002784449b", :adapter => 1
    db2.ssh.forward_agent = true
  end

  config.vm.define "db3" do |db3|
    db3.vm.hostname = "db3"
#    db3.vm.network "private_network", ip: "192.168.22.33"
    db3.vm.network "public_network", bridge: "oms0", :mac => "08002784449c", :adapter => 1
    db3.ssh.forward_agent = true
  end

end

