## Configuración de Router-VoIP Sede Tena
    #R-VoIP
    reload
    no
    enable
    configure terminal
    hostname R_ST_VoIP
    ip dhcp pool R_ST_VOIP
    network 210.32.1.0 255.255.255.0
    default-router 210.32.1.1
    option 150 ip 210.32.1.1
    interface f0/0
    ip address 210.32.1.1 255.255.255.0
    no shutdown
    telephony-service
    max-ephones 2
    max-dn 2
    ip source-address 210.32.1.1 port 2000
    auto assign 1 to 2
    exit
    ephone-dn 1
    number 1156
    ephone-dn 2
    number 1166
