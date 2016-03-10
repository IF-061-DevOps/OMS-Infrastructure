# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure(2) do |config|

  config.vm.provision "shell", :inline => "sudo cp /home/vagrant/sync/hosts /etc/hosts", run: "always"

  config.vm.define "ansible" do |ansible|
    ansible.vm.box = "centos/7"
    ansible.vm.hostname = "ansible.devops.local"
    ansible.vm.network "private_network", ip: "192.168.22.10" 
    ansible.vm.provision "shell", inline: <<-SHELL
      sudo yum install epel-release -y
      sudo yum install PyYAML python-httplib2 python-jinja2 python-keyczar python-paramiko python-setuptools python-six sshpass -y
      sudo yum install ansible.rpm http://releases.ansible.com/ansible-network/2.0.1.0-0.2/ansible-2.0.1.0-0.2.network.el7.centos.noarch.rpm -y
SHELL
    ansible.ssh.forward_agent = true
  end

  config.vm.define "balancer" do |balancer|
    balancer.vm.box = "centos/7"
    balancer.vm.hostname = "balancer"
    balancer.vm.network "private_network", ip: "192.168.22.11"
    balancer.vm.network "public_network", bridge: "eth0"
    balancer.ssh.forward_agent = true
  end

  config.vm.define "jenkins" do |jenkins|
    jenkins.vm.box = "centos/7"
    jenkins.vm.hostname = "jenkins"
    jenkins.vm.network "private_network", ip: "192.168.22.12"
    jenkins.ssh.forward_agent = true
  end

  config.vm.define "zabbix" do |zabbix|
    zabbix.vm.box = "centos/7"
    zabbix.vm.hostname = "zabbix"
    zabbix.vm.network "private_network", ip: "192.168.22.13"
    zabbix.ssh.forward_agent = true
  end

  config.vm.define "repo" do |repo|
    repo.vm.box = "centos/7"
    repo.vm.hostname = "repo"
    repo.vm.network "private_network", ip: "192.168.22.14"
    repo.ssh.forward_agent = true
  end

  config.vm.define "logs" do |logs|
    logs.vm.box = "centos/7"
    logs.vm.hostname = "logs"
    logs.vm.network "private_network", ip: "192.168.22.15"
    logs.ssh.forward_agent = true
  end

  config.vm.define "web1" do |web1|
    web1.vm.box = "centos/7"
    web1.vm.hostname = "web1"
    web1.vm.network "private_network", ip: "192.168.22.21"
    web1.ssh.forward_agent = true
  end

  config.vm.define "web2" do |web2|
    web2.vm.box = "centos/7"
    web2.vm.hostname = "web2"
    web2.vm.network "private_network", ip: "192.168.22.22"
    web2.ssh.forward_agent = true
  end

  config.vm.define "web3" do |web3|
    web3.vm.box = "centos/7"
    web3.vm.hostname = "web3"
    web3.vm.network "private_network", ip: "192.168.22.23"
    web3.ssh.forward_agent = true
  end

  config.vm.define "db1" do |db1|
    db1.vm.box = "centos/7"
    db1.vm.hostname = "db1"
    db1.vm.network "private_network", ip: "192.168.22.31"
    db1.ssh.forward_agent = true
  end

  config.vm.define "db2" do |db2|
    db2.vm.box = "centos/7"
    db2.vm.hostname = "db2"
    db2.vm.network "private_network", ip: "192.168.22.32"
    db2.ssh.forward_agent = true
  end

  config.vm.define "db3" do |db3|
    db3.vm.box = "centos/7"
    db3.vm.hostname = "db3"
    db3.vm.network "private_network", ip: "192.168.22.33"
    db3.ssh.forward_agent = true
  end

end
