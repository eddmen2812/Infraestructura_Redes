## Configuración ROuter de VoIP
    #R-VoIP
    reload
    no
    enable
    configure terminal
    hostname R_VoIP
    ip dhcp pool R_VOIP
    network 200.70.1.0 255.255.255.0
    default-router 200.70.1.1
    option 150 ip 200.70.1.1
    ip address 200.70.1.1 255.255.255.0
    no shutdown
    telephony-service
    max-ephones 6
    max-dn 6
    ip source-address 200.70.1.1 port 2000
    auto assign 1 to 6
    exit
    ephone-dn 1
    number 6316
    ephone-dn 2
    number 6317
    ephone-dn 3
    number 6318
    ephone-dn 4
    number 6319
    ephone-dn 5
    number 6320
    ephone-dn 6
    number 6321
    spanning-tree mode rapid-pvst

