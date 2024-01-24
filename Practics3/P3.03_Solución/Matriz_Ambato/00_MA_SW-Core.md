## Configuración del Switch Core
    #SW-Core
    enable
    configure terminal
    hostname SW-Core
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
    name WLC
    #vlan 25
    #name ROUTE
---
    configure terminal
    interface range g1/0/1 - 8
    switchport mode trunk
    interface g1/0/9
    switchport mode access
    switchport access vlan 21
    interface range g1/0/11 - 12
    switchport mode access
    switchport access vlan 21
    interface g1/0/24
    switchport mode access
    switchport access vlan 24
    #interface g1/0/23
    #switchport mode access
    #switchport access vlan 25
--- 
##### ip para routear///////////////////////////////////
    interface g1/0/23
    no switchport
    ip address 199.25.88.2 255.255.255.252
    ip default-gateway 199.25.88.1
    interface g1/0/23
    ipv6 address 2134:db9:bb:88::2/64
##### conf eigrp
    interface vlan21
    ipv6 eigrp 115

---
    ip routing
    ipv6 unicast-routing
    interface vlan10
    ip address 200.70.10.1 255.255.255.0
    ipv6 address 2001:db8:bb:10::1/64
    interface vlan11
    ip address 200.70.11.1 255.255.255.0
    ipv6 address 2001:db8:bb:11::1/64
    interface vlan12
    ip address 200.70.12.1 255.255.255.0
    ipv6 address 2001:db8:bb:12::1/64
    interface vlan13
    ip address 200.70.13.1 255.255.255.0
    ipv6 address 2001:db8:bb:13::1/64
    interface vlan14
    ip address 200.70.14.1 255.255.255.0
    ipv6 address 2001:db8:bb:14::1/64
    interface vlan15
    ip address 200.70.15.1 255.255.255.0
    ipv6 address 2001:db8:bb:15::1/64
    interface vlan16
    ip address 200.70.16.1 255.255.255.0
    ipv6 address 2001:db8:bb:16::1/64
    interface vlan17
    ip address 200.70.17.1 255.255.255.0
    ipv6 address 2001:db8:bb:17::1/64
    interface vlan18
    ip address 200.70.18.1 255.255.255.0
    ipv6 address 2001:db8:bb:18::1/64
    interface vlan19
    ip address 200.70.19.1 255.255.255.0
    ipv6 address 2001:db8:bb:19::1/64
    interface vlan20
    ip address 200.70.20.1 255.255.255.0
    ipv6 address 2001:db8:bb:20::1/64
    interface vlan21
    ip address 200.70.21.1 255.255.255.0
    ipv6 address 2001:db8:bb:21::1/64
    interface vlan22
    ip address 200.70.22.1 255.255.255.0
    ipv6 address 2001:db8:bb:22::1/64
    interface vlan23
    ip address 200.70.23.1 255.255.255.0
    ipv6 address 2001:db8:bb:23::1/64
    interface vlan2
    ip address 200.70.2.1 255.255.255.0
    ipv6 address 2001:db8:bb:2::1/64
    interface vlan24
    ip address 200.70.24.1 255.255.255.0
    ipv6 address 2001:db8:bb:24::1/64
---
    interface vlan10
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan11
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan12
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan13
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan14
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan15
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan16
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan17
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan18
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan19
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan20
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan21
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan22
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan23
    ip helper-address 200.70.21.2
    ipv6 dhcp relay 2001:db8:bb:21::2
    interface vlan24
    ip helper-address 200.70.21.2
---
    spanning-tree vlan 1-50 priority 0
    interface range g1/0/11 - 12
    spanning-tree portfast
    interface g1/0/9
    spanning-tree portfast
    interface g1/0/10
    spanning-tree portfast
    interface g1/0/24
    spanning-tree portfast
    interface g1/0/23
    spanning-tree portfast
    spanning-tree mode rapid-pvst
----
##### ntp/////////////////////////
    #clock set 15:20:00 september 06 2023
    configure terminal
    ntp server 200.70.21.4
    ntp update-calendar
    #show ntp associations
---

