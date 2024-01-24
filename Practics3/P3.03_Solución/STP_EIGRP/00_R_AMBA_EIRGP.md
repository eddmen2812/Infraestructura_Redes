## Configuración EIGRP ROUTER AMBATO
    #Router3-Ambato
    enable
    configure terminal
    hostname R-EIGRP-Ambato
    interface g0/0
    ip address 199.25.88.1 255.255.255.252
    ipv6 address 2134:db9:bb:88::1/64
    no shutdown
    interface g0/1
    ip address 4.4.4.1 255.255.255.252
    ipv6 address 2800:4:4:4::1/64
    no shutdown
    interface s0/0/0
    ip address 2.2.2.1 255.255.255.252
    ipv6 address 2800:2:2:2::1/64
    no shutdown
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
    ipv6 router eigrp 115
    eigrp router-id 1.1.1.1
    passive-interface g0/0
    no shutdown
    interface g0/0
    ipv6 eigrp 115
    interface s0/0/0
    ipv6 eigrp 115
    interface g0/1
    ipv6 eigrp 115
##### Conf ipv4//////////////////
    ip routing
    router eigrp 100
    eigrp router-id 1.1.1.2
    passive-interface g0/0
    no auto-summary
    network 199.25.88.0 #255.0.0.0
    network 2.2.2.0 #255.0.0.0
    network 4.4.4.0 #255.0.0.0