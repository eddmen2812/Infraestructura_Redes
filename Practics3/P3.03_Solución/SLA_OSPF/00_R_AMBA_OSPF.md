## Configuración OSPF ROUTER AMBATO
    #Router3-Ambato
    enable
    configure terminal
    hostname R-OSPF-Ambato
    interface s0/1/0
    ip address 6.6.6.1 255.255.255.252
    ipv6 address 2800:6:6:6::1/64
    no shutdown
    interface s0/0/1
    ip address 8.8.8.1 255.255.255.252
    ipv6 address 2800:8:8:8::1/64
    no shutdown
    exit
    enable secret UTJLM@2023
    line console 0
    logging synchronous
    password Ambato@2023
    login
    service password-encryption
##### Conf ipv6//////////////////
    ipv6 unicast-routing
    ipv6 router ospf 10
    router-id 1.1.2.2
    passive-interface g0/0
    #interface g0/0
    #ipv6 ospf 10 area 0
    interface s0/1/0
    ipv6 ospf 10 area 0
    interface s0/0/1
    ipv6 ospf 10 area 0
##### Conf ipv4//////////////////
    ip routing
    router ospf 1
    #router-id 1.1.2.2
    #passive-interface g0/0
    #network 199.25.88.0 255.255.255.252 area 0
    network 6.6.6.0 255.255.255.252 area 0
    network 8.8.8.0 255.255.255.252 area 0