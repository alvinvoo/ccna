Router CLI commands

```
router>? # show all commands
router>enable # priviledge mode
- # type something and press tab to autocomplete
Router>enable ? # question mark shows other options
  <0-15>  Enable level
  view    Set into the existing view
  <cr>
..
Router#show version   # show router version and info
...
Router#conf terminal   # switch to config terminal mode
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#hos
Router(config)#hostname R1
R1(config)#interface gigabitEthernet 0/0
R1(config-if)#no shutdown    # no shutdown enables the interface, by default, router interface are shutdown
R1(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

.. # configuring ip

R1(config-if)#ip address 10.1.1.1 255.255.255.0  # ip address subnet mask
R1(config-if)#end   # to exit config t mode
R1#
%SYS-5-CONFIG_I: Configured from console by console

.. # once switch is up
R1#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up
R1#ping 10.1.1.1   # can ping myself

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 0/2/6 ms

R1#wr  #write, save config
Building configuration...
[OK]

```

```
# from R2
R2#ping 10.1.1.2

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.2, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 0/3/9 ms

R2#ping 10.1.1.1

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
.!!!!    #<--- first ping timesout, because this router has to ARP the MAC address of the other router
Success rate is 80 percent (4/5), round-trip min/avg/max = 0/0/0 ms

R2#copy running-config startup-config   # save current config as start up config
Destination filename [startup-config]? 
Building configuration...
[OK]

R2#show running-config    # show running config
Building configuration...

Current configuration : 652 bytes
!
!...
```

**NOTE, to simulate real life, 
instead of accessing the cli of switch/router straight
connect a PC/laptop with _console cable_ to the switch/router, and access via their terminals

## Switch commands:
- Switch by default is powered off
- Need to add a `AC-POWER-SUPPLY` power module in the switch (physical view) to power it up
- Switch interface by default are up, Router interface by default are down so we need to `enable` them

#### MISC stuffs
*Spanning tree
- interface starts with Orange (dot) because of Spanning tree
- A way to stop loops in an Ethernet network
- It takes a while for spanning tree to _converge_ after making sure everything is good

*ARP
- Address Resolution Protocol
