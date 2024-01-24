## Configuración de Router-VoIP Sede Puyo
    #R-VoIP
    reload
    no
    enable
    configure terminal
    hostname R_SP_VoIP
    ip dhcp pool R_SP_VOIP
    network 195.28.1.0 255.255.255.0
    default-router 195.28.1.1
    option 150 ip 195.28.1.1
    interface f0/0
    ip address 195.28.1.1 255.255.255.0
    no shutdown
    telephony-service
    max-ephones 2
    max-dn 2
    ip source-address 195.28.1.1 port 2000
    auto assign 1 to 2
    exit
    ephone-dn 1
    number 2580
    ephone-dn 2
    number 2590
