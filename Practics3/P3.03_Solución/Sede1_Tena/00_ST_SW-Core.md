## Configuración SW Core de Tena
    #SW-Core_TENA
    enable
    configure terminal
    hostname SW-Core_TENA
    vlan 10
    name DOCE
---
    configure terminal
    interface range g1/0/1 - 2
    switchport mode trunk
---
##### ip para routear///////////////////////////////////
    interface g1/0/24
    no switchport
    ip address 210.10.32.2 255.255.255.252
    ipv6 address 2500:db5:bb:32::2/64
    ipv6 eigrp 115
---
    ip routing
    ipv6 unicast-routing
    interface vlan10
    ip address 210.32.10.1 255.255.255.0
    ipv6 address 2500:db5:cafe:10::1/64
---
    #interface vlan10
    #ip helper-address 210.32.10.1
    #ipv6 dhcp relay 2001:db8:bb:21::2-----ipv6 servider dhcp
---
    spanning-tree vlan 1-50 priority 0
    interface g1/0/10
    spanning-tree portfast
    interface g1/0/24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
---


