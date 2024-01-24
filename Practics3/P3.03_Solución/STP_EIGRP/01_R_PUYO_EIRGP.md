## Configuración EIGRP ROUTER PUYO
    #Router2-PUYO
    enable
    configure terminal
    hostname R-EIGRP-PUYO
    interface g0/0
    ip address 195.20.28.1 255.255.255.252
    ipv6 address 2600:db6:cafe:280::1/64
    no shutdown
    exit
    interface s0/0/1
    ip address 3.3.3.2 255.255.255.252
    ipv6 address 2800:3:3:3::2/64
    no shutdown
    interface s0/0/0
    ip address 2.2.2.2 255.255.255.252
    ipv6 address 2800:2:2:2::2/64
    no shutdown
    exit
    enable secret UTJLM@2023
    line console 0
    logging synchronous
    password Alausi@2023
    login
    service password-encryption
##### Conf ipv6//////////////////
    ipv6 unicast-routing
    ipv6 router eigrp 115
    eigrp router-id 2.2.2.2
    #passive-interface g0/0
    no shutdown
    interface g0/0
    ipv6 eigrp 115
    interface s0/0/0
    ipv6 eigrp 115
    interface s0/0/1
    ipv6 eigrp 115
##### Conf ipv4//////////////////
    ip routing
    router eigrp 100
    eigrp router-id 2.2.2.3
    #passive-interface g0/0
    no auto-summary
    network 195.20.28.0  #255.0.0.0
    network 3.3.3.0  #255.0.0.0
    network 2.2.2.0  #255.0.0.0
---------------------------------------------------------------