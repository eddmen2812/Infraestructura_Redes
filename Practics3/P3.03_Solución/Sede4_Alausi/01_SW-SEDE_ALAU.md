## Configuración SW-Alausi
    #SW-SEDE_ALAU
    enable
    configure terminal
    hostname SW-SEDE_ALAU
    vlan 40
    name INVE
---
    interface g0/1
    switchport mode trunk
    interface range f0/1 -2
    switchport mode access
    switchport access vlan 40
---
    interface range f0/1 - 15
    spanning-tree portfast
    interface range f0/20 - 24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
---
    interface range f0/23 - 24
    switchport voice vlan 1
