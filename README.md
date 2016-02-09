# OMS-Infrastructure

Local infrastructure opened on Vagrant VirtualBox

OS: CentOS 7

Network: 192.168.22.0/24

### Hosts

- ansible (192.168.22.10)
- balancer (192.168.22.11, +EXT IP)
- jenkins (192.168.22.12)
- zabbix (192.168.22.13)
- repo (192.168.22.14)
- rsyslog (192.168.22.15)
- web1 (192.168.22.21)
- web2 (192.168.22.22)
- web3 (192.168.22.23)
- db1 (192.168.22.31)
- db2 (192.168.22.32)

Up/Down all virtual hosts ```vagrant up``` / ```vagrant halt```

Up/Down single virtual host ```vagrant up ansible``` / ```vagrant halt ansible```

