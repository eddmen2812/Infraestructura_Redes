## Configuración OSPF ROUTER ALAUSI
    #Router-ALAUSI
    enable
    configure terminal
    hostname R-OSPF-ALAU
    interface g0/0
    ip address 222.40.234.1 255.255.255.252
    ipv6 address 2800:db6:cafe:234::1/64
    no shutdown
    exit
    interface g0/1
    ip address 10.10.10.2 255.255.255.252
    ipv6 address 2800:10:10:10::2/64
    no shutdown
    interface s0/0/1
    ip address 8.8.8.2 255.255.255.252
    ipv6 address 2800:8:8:8::2/64
    no shutdown
    exit
    enable secret UTJLM@2023
    line console 0
    logging synchronous
    password Puyo@2023
    login
    service password-encryption
##### Conf ipv6//////////////////
    ipv6 unicast-routing
    ipv6 router ospf 15
    router-id 2.2.3.3
    #passive-interface g0/0
    interface g0/0
    ipv6 ospf 15 area 0
    interface g0/1
    ipv6 ospf 15 area 0
    interface s0/1/0
    ipv6 ospf 15 area 0
##### Conf ipv4//////////////////
    ip routing
    router ospf 1
    #router-id 1.1.2.2
    #passive-interface g0/0
    network 222.40.234.0 255.255.255.252 area 0
    network 6.6.6.0 255.255.255.252 area 0
    network 10.10.10.0 255.255.255.252 area 0
---------------------------------------------------------------