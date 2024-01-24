## Configuración Switch Informática
    #SW-INFO
    enable
    configure terminal
    hostname SW-INFO
    vlan 2
    name IMPR
    vlan 10
    name SECR
    vlan 11
    name TALH
    vlan 12
    name FINA
    vlan 13
    name BIBL
    vlan 10
    name SECR
    vlan 11
    name TALH
    vlan 12
    name FINA
    vlan 13
    name BIBL
    vlan 14
    name DOCE
    vlan 15
    name COOR
    vlan 16
    name PROC
    vlan 17
    name DIRE
    vlan 18
    name SOCA
    vlan 19
    name MANS
    vlan 20
    name DESA
    vlan 21
    name SERV
    vlan 22
    name VINC
    vlan 23
    name CENI
    vlan 24
    name WCL
---
    configure terminal
    interface g0/1
    switchport mode trunk
    interface f0/23
    switchport mode access
    switchport access vlan 2
    interface range f0/1 -2
    switchport mode access
    switchport access vlan 18
    interface range f0/3 - 4
    switchport mode access
    switchport access vlan 19
    interface range f0/5 - 6
    switchport mode access
    switchport access vlan 20
    interface range f0/7 - 8
    switchport mode access
    switchport access vlan 10
    interface f0/22
    switchport mode access
    switchport access vlan 24
---
    interface range f0/1 - 15
    spanning-tree portfast
    interface range f0/20 - 24
    spanning-tree portfast
    spanning-tree mode rapid-pvst
---
    interface f0/24
    switchport voice vlan 1
##### ntp/////////////////////////
    ntp server 200.70.10.1
##### chaner_grouo////////////////////////
    interface range f0/10 - 11
    channel-group 2 mode passive
    interface port-channel 2
    switchport mode trunk
    interface range f0/14 - 15
    channel-group 3 mode active
    interface port-channel 3
    switchport mode trunk