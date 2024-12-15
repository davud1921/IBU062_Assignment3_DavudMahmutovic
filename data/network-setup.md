Router1:
    Device Model: 1941
    Hostname: Router


Switch1:
    Device Model: 2960 IOS15
    Hostname: Switch
Switch2:
    Device Model: 2960 IOS15
    Hostname: Switch


Server1:
    Device Model: Server-PT
    IP Address: 168.90.0.5
Server2:
    Device Model: Server-PT
    IP Address: 210.3.14.2   
Server3:
    Device Model: Server-PT
    IP Address: 210.3.14.4      


PC1:
    Device Model: PC-PT
    IP Address: 168.90.0.4
PC2:
    Device Model: PC-PT
    IP Address: 168.90.0.3
PC3:
    Device Model: PC-PT
    IP Address: 210.3.14.3
PC4:
    Device Model: PC-PT
    IP Address: 168.90.0.6
PC5:
    Device Model: PC-PT
    IP Address: 210.3.14.5        


Laptop:
    Device Model: Laptop-PT
    IP Address: 168.90.0.4


DHCP Details:
    configure terminal
    ip dhcp pool Switch1
    network 168.90.0.0 255.255.0.0
    default-router 168.90.0.1
    exit

    configure terminal
    ip dhcp pool Switch2
    network 210.3.14.0 255.255.255.0
    default-router 210.3.14.1
    exit

    configure terminal
    ip dhcp excluded-address 168.90.0.1
    ip dhcp excluded-address 210.3.14.1
    exit

    configure terminal
    interface GigabitEthernet0/0
    ip address 168.90.0.1 255.255.0.0
    no shutdown

    interface GigabitEthernet0/1
    ip address 210.3.14.1 255.255.255.0
    no shutdown
    exit                     