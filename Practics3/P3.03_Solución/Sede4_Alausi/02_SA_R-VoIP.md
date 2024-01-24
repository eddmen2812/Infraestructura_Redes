## Configuración de Router-VoIP Sede Alausi
    #R-VoIP
    reload
    no
    enable
    configure terminal
    hostname R_SA_VoIP
    ip dhcp pool R_SA_VOIP
    network 222.234.1.0 255.255.255.0
    default-router 222.234.1.1
    option 150 ip 222.234.1.1
    interface f0/0
    ip address 222.234.1.1 255.255.255.0
    no shutdown
    telephony-service
    max-ephones 2
    max-dn 2
    ip source-address 222.234.1.1 port 2000
    auto assign 1 to 2
    exit
    ephone-dn 1
    number 7996
    ephone-dn 2
    number 7010
