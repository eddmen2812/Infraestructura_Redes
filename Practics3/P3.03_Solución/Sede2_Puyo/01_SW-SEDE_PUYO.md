## Configuración SW-Puyo
    #SW-SEDE_LATA
    enable
    configure terminal
    hostname SW-SEDE_PUYO
    vlan 20
    name PREG
    ---
    interface g0/1
    switchport mode trunk
    interface range f0/1 -2
    switchport mode access
    switchport access vlan 20
    ---
    interface range f0/1 - 15
    spanning-tree portfast
    interface range f0/20 - 24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
    ---
    interface range f0/23 - 24
    switchport voice vlan 1
