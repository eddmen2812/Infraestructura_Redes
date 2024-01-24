## Configuración SW Core de Puyo
    #SW-Core_PUYO
    enable
    configure terminal
    hostname SW-Core_PUYO
    vlan 20
    name PREG
---
    configure terminal
    interface range g1/0/1 - 2
    switchport mode trunk
##### ip para routear///////////////////////////////////
    interface g1/0/24
    no switchport
    ip address 195.28.5.1 255.255.255.0
    ipv6 address 2600:DB6:CAFE:5::1/64
    ipv6 eigrp 115
---
    ip routing
    ipv6 unicast-routing
    interface vlan20
    ip address 195.28.20.1 255.255.255.0
    ipv6 address 2600:db6:cafe:20::1/64
---
    #interface vlan20
    #ip helper-address 195.28.20.1
    #ipv6 dhcp relay 2001:db8:bb:21::2-----ipv6 servider dhcp
---
    spanning-tree vlan 1-50 priority 0
    interface g1/0/10
    spanning-tree portfast
    interface g1/0/24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
---


