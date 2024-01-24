## Configuración SW Core de Alausi
    #SW-Core_ALAU
    enable
    configure terminal
    hostname SW-Core_ALAU
    vlan 40
    name INVE
---
    configure terminal
    interface range g1/0/1 - 2
    switchport mode trunk
##### ip para router/////////////////////////////
    interface g1/0/24
    no switchport
    ip address 222.40.234.2 255.255.255.252
    ipv6 addres  2800:db6:cafe:234::2
    interface vlan40
    ipv6 ospf 15 area 0
---
    ip routing
    ipv6 unicast-routing
    interface vlan40
    ip address 222.234.40.1 255.255.255.0
    ipv6 address 2800:db8:cafe:40::1/64
---
    #interface vlan20
    #ip helper-address 222.234.40.1
    #ipv6 dhcp relay 2001:db8:bb:21::2-----ipv6 servider dhcp
---
    spanning-tree vlan 1-50 priority 0
    interface g1/0/10
    spanning-tree portfast
    interface g1/0/24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
---


