## Enrutamiento Dinámico y Estático
El t ́ermino enrutamiento se refiere a tomar un paquete de un dispositivo y enviarlo a trav ́es de la red a otro dispositivo en una red diferente.
A los enrutadores realmente no les importan los hosts, solo les importan las redes y la mejor ruta para cada una de ellas.
### Configuración de Enrutamiento Estático
Requiere que alguien escriba a mano todas las ubicaciones de la red en la tabla de enrutamiento.
    enable
    configure terminal
    hostname R_Gerencia
    interface serial 0/0/0
    ip address 10.0.0.1 255.255.255.252
    clock rate 128000
    no shut down
    interface serial 0/0/1
    ip address 10.0.0.5 255.255.255.252
    clock rate 128000
    no shutdown
    interface gigabitEthernet 192.168.1.1 255.255.255.0
    no shut down now
    do copy running-config startup-config

    enable
    configure terminal
    hostname R_Almacen
    interface serial 0/0/0
    ip address 10.0.0.2 255.255.255.252
    no shut down
    interface gigabitEthernet 0/0 
    ip address 192.168.1.1 255.255.255.0
    no shut down now
    do copy running-config startup-config

    enable
    configure terminal
    hostname R_Ventas
    interface serial 0/0/0
    ip address 10.0.0.6 255.255.255.252
    no shut down
    interface gigabitEthernet 0/0 
    ip address 192.168.1.1 255.255.255.0
    no shut down now
    do copy running-config startup-config

    para gerencia
    configure terimal
    ip route 192.168.2.0 255.255.255.0 10.0.0.2
    ip route 192.168.3.0 255.255.255.0 10.0.0.6

    almacen
    enable
    configure terminal
    ip route 10.0.0.4 255.255.255.0 10.0.0.1
    ip route 192.168.1.0 255.255.255.0 10.0.0.1
    ip route 192.168.3.0 255.255.255.0 10.0.0.1

    ventas
    enable
    configure terminal
    ip route 10.0.0.0 255.255.255.252 10.0.0.5
    ip route 192.168.1.0 255.255.255.0 10.0.0.5
    ip route 192.168.2.0 255.255.255.0 10.0.0.5

    gerenncia
    enable
    configure terminal
    ip route 0.0.0.0 0.0.0.0 10.0.0.2
    ip route 0.0.0.0 0.0.0.0 10.0.0.6
    do copy running-config startup-config

    alamcen
    enable
    configure terminal
    ip route 0.0.0.0 0.0.0.0 10.0.0.1
    do copy running-config startup-config

    ventas
    enable
    configure terminal
    ip route 0.0.0.0 0.0.0.0 10.0.0.5
    do copy running-config startup-config
### Configuración Dinámica
Un protocolo en un enrutador se comunica
con el mismo protocolo que se ejecuta en los enrutadores vecinos.
Luego, los enrutadores se actualizan entre s ́ı sobre todas las redes que conocen y colocan esta informaci ́on en la tabla de enrutamiento. Si ocurre un cambio en la red, los protocolos informan autom ́aticamente a todos los enrutadores.

    Configurar RIP
    gerencia
    enable
    configure terminal
    router rip
    network 10.0.0.0
    network 10.0.0.4
    network 192.168.1.0
    do copy running-config startup-config

    alamcen
    enable
    configure terminal
    router rip
    network 10.0.0.0
    network 192.168.2.0
    do copy running-config startup-config

    ventas
    enable
    configure terminal
    router rip
    network 10.0.0.4
    network 192.168.3.0
    do copy running-config startup-config


    gerencia
    router ospf 1
    network 10.0.0.0 0.0.0.3 area 1
    network 10.0.0.4 0.0.0.3 area 1
    nwtwork 192.168. area 1

    alamcen
    router ospf 1
    network 10.0.0.0 0.0.0.3 area 1
    nwtwork 192.168.2.0 0.0.0.255 area 1

    ventas
    router ospf 1
    network 10.0.0.4 0.0.0.3 area 1
    nwtwork 192.168.3.0 0.0.0.255 area 1
