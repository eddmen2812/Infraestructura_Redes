## Configuración SW-Latacunga
    #SW-SEDE_LATA
    enable
    configure terminal
    hostname SW-SEDE_LATA
    vlan 30
    name POST
---
    interface g0/1
    switchport mode trunk
    interface range f0/1 -2
    switchport mode access
    switchport access vlan 30
---
    interface range f0/1 - 15
    spanning-tree portfast
    interface range f0/20 - 24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
---
    interface range f0/23 - 24
    switchport voice vlan 1
