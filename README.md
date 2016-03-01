# OMS-Infrastructure

Local infrastructure opened on Vagrant VirtualBox

OS: CentOS 7

Network: 192.168.22.0/24

### Hosts

- [ansible]
    - ansible (192.168.22.10)
- [balancer] 
    - balancer (192.168.22.11, +EXT IP)
- [ci]    
    - jenkins (192.168.22.12)
- [monitoring]
    - zabbix (192.168.22.13)
    - logs (192.168.22.15)
- repo (192.168.22.14)
- [webapp]
    - web1 (192.168.22.21)
    - web2 (192.168.22.22)
    - web3 (192.168.22.23)
- [database]    
    - db1 (192.168.22.31)
    - db2 (192.168.22.32)
    - db3 (192.168.22.33)

Up/Down all virtual hosts ```vagrant up``` / ```vagrant halt```

Up/Down single virtual host ```vagrant up ansible``` / ```vagrant halt ansible```

