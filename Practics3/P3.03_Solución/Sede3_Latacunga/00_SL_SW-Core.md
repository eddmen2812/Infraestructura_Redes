## Configuración SW Core de Latacunga
    #SW-Core_LATA
    enable
    configure terminal
    hostname SW-Core_LATA
    vlan 30
    name POST
---
    configure terminal
    interface range g1/0/1 - 2
    switchport mode trunk
##### ip para route///////////////////////
    interface g1/0/24
    no switchport
    ip address 193.30.123.2 255.255.255.252
    ipv6 addres  2700:db6:cafe:123::2
    interface vlan30
    ipv6 ospf 23 area 0
---
    ip routing
    ipv6 unicast-routing
    interface vlan30
    ip address 193.123.30.1 255.255.255.0
    ipv6 address 2700:af7:cafe:30::1/64
---
    #interface vlan20
    #ip helper-address 193.123.30.1
    #ipv6 dhcp relay 2001:db8:bb:21::2-----ipv6 servider dhcp
---
    spanning-tree vlan 1-50 priority 0
    interface g1/0/10
    spanning-tree portfast
    interface g1/0/24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
---


