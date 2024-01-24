## Configuración Inicial
![Alt text](/img/img_practicas//image1.png)
    
    R1
    enable
    configure terminal
    hostname R1
    interface G0/0/0
    ip address 192.168.1.1 255.255.255.0
    description RED-LAN
    no shutdown  ->No apagar-> Habilitar
    end

    SW1
    enable
    configure terminal
    hostname SW1
    interface vlan 1
    ip address 192.168.1.2 255.255.255.0
    description RED-LAN
    no shutdown  ->No apagar-> Habilitar
    exit

    #show ip interface brief
    #show running-config
    #show startup-config
    #copy runnning-config startup-config -> copy run start
    #write -> wr
    #ping- >cerficación de conexión
    (config)#do show running-config
    (config)#do show ip interface brief
    OJO-> Examen de certificación-> USAR COMANDO COMPLETOS
                                -> NO USAR TAB
                                -> NO USAR WRITE
                                -> Guardar siempre todo cambio



    PC
    Direccion IP: 192.168.1.10
    Mascara:       255.255.255.0
    Gateway:       192.168.1.1 (Direccion IP de la Interface del Router en esta red)

    #ipconfig
    #ping

    ---------------------------------
    TELNET

    R1
    enable
    configure terminal
    no ip domain-lookup
    !enable password cisco
    enable secret cisco
    banner motd .SOLO PERSONAL AUTORIZADO .
    line console 0
    password cisco
    login
    exec-timeout 10 10
    exit
    line vty 0 4
    password cisco
    login
    exec-timeout 10
    exit

    service password-encryption

    PC: telnet 192.168.1.1

    ------------------------------
    SSH
    SW1
    enable
    configure terminal
    no ip domain-lookup
    hostname SW1
    ip domain-name cisco.com
    crypto key generate rsa general-key modulus 2000
    banner motd .SOLO PERSONAL AUTORIZADO .
    enable secret cisco

    !username cisco password cisco
    username cisco secret cisco
    username paul secret paul

    line console 0
    password cisco
    login

    line vty 0 4
    exec-timeout 5 
    login local

    service password-encryption


    PC: ssh -l cisco 192.168.1.2