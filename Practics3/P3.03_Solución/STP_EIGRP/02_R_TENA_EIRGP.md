## Configuración EIGRP ROUTER TENA
    #Router-TENA
    enable
    configure terminal
    hostname R-EIGRP-TENA
    interface g0/0
    ip address 210.10.32.1 255.255.255.0
    ipv6 address 2500:DB5:CAFE:5::1/64
    no shutdown
    exit
    interface g0/1
    ip address 4.4.4.2 255.255.255.252
    ipv6 address 2800:4:4:4::2/64
    no shutdown
    interface s0/0/1
    ip address 3.3.3.1 255.255.255.252
    ipv6 address 2800:3:3:3::1/64
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
    ipv6 router eigrp 115
    eigrp router-id 3.3.3.3
    #passive-interface g0/0
    no shutdown
    interface g0/1
    ipv6 eigrp 115
    interface s0/0/1
    ipv6 eigrp 115
    interface g0/0
    ipv6 eigrp 115
##### Conf ipv4//////////////////
    ip routing
    router eigrp 100
    eigrp router-id 3.3.3.4
    #passive-interface g0/0
    no auto-summary
    network 210.10.32.0 #255.0.0.0
    network 4.4.4.0 #255.0.0.0
    network 3.3.3.0 #255.0.0.0
---------------------------------------------------------------