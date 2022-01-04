# VLAN configuration
Virtual Local Area Networks (VLAN)
![VLAN](https://user-images.githubusercontent.com/26889268/148002683-8befb9f7-3117-4ade-9c8b-abf35ec87eb7.png)

## Let's start

***After opening packate tracer we need to complete a design like the image.***

### For switch 0 and 1
```Switch>enab  
Switch>enable 
Switch#conf t  
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#
Switch(config)#vl
Switch(config)#vlan 2
Switch(config-vlan)#name Reporting
Switch(config-vlan)#inter
Switch(config-vlan)#interface range fa 0/1-2
Switch(config-if-range)#sw
Switch(config-if-range)#switchport acc
Switch(config-if-range)#switchport access vl
Switch(config-if-range)#switchport access vlan 2
Switch(config-if-range)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#vlan 3
Switch(config-vlan)#name Editing
Switch(config-vlan)#inter
Switch(config-vlan)#interface range fa 0/3-4
Switch(config-if-range)#sw
Switch(config-if-range)#switchport acc
Switch(config-if-range)#switchport access vla
Switch(config-if-range)#switchport access vlan 3
Switch(config-if-range)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#vlan 4
Switch(config-vlan)#name Proofing
Switch(config-vlan)#interface range fa 0/5-6
Switch(config-if-range)#sw
Switch(config-if-range)#switchport acc
Switch(config-if-range)#switchport access vla
Switch(config-if-range)#switchport access vlan 4
Switch(config-if-range)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#vlan 5
Switch(config-vlan)#name Finishing
Switch(config-vlan)#interface range fa 0/7-8
Switch(config-if-range)#sw
Switch(config-if-range)#switchport acc
Switch(config-if-range)#switchport access vlan 5
Switch(config-if-range)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#interface range fa 0/1-8
Switch(config-if-range)#sw
Switch(config-if-range)#switchport mode acc
Switch(config-if-range)#switchport mode access 
Switch(config-if-range)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#interface g 0/1
Switch(config-if)#sw
Switch(config-if)#switchport mode trunk
Switch(config-if)#exit
Switch(config)#do wr
Building configuration...
[OK]
Switch(config)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#do wr
Building configuration...
[OK]
Switch(config)#exit


Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#show vlan bri
Switch#show vlan brief 

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa0/9, Fa0/10, Fa0/11, Fa0/12
                                                Fa0/13, Fa0/14, Fa0/15, Fa0/16
                                                Fa0/17, Fa0/18, Fa0/19, Fa0/20
                                                Fa0/21, Fa0/22, Fa0/23, Fa0/24
                                                Gig0/2
2    Reporting                        active    Fa0/1, Fa0/2
3    Editing                          active    Fa0/3, Fa0/4
4    Proofing                         active    Fa0/5, Fa0/6
5    Finishing                        active    Fa0/7, Fa0/8
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active    


Switch#sh
Switch#show interface sw
Switch#show interface switchport 
Name: Fa0/1
Switchport: Enabled
Administrative Mode: static access
Operational Mode: static access
Administrative Trunking Encapsulation: dot1q
Operational Trunking Encapsulation: native
Negotiation of Trunking: Off
Access Mode VLAN: 2 (Reporting)
Trunking Native Mode VLAN: 1 (default)
Voice VLAN: none
Administrative private-vlan host-association: none
Administrative private-vlan mapping: none
Administrative private-vlan trunk native VLAN: none
Administrative private-vlan trunk encapsulation: dot1q
Administrative private-vlan trunk normal VLANs: none
Administrative private-vlan trunk private VLANs: none
Operational private-vlan: none
Trunking VLANs Enabled: All
Pruning VLANs Enabled: 2-1001
Capture Mode Disabled
Capture VLANs Allowed: ALL
Protected: false


Switch#show interface trunk
Port        Mode         Encapsulation  Status        Native vlan
Gig0/1      on           802.1q         trunking      1

Port        Vlans allowed on trunk
Gig0/1      1-1005

Port        Vlans allowed and active in management domain
Gig0/1      1,2,3,4,5

Port        Vlans in spanning tree forwarding state and not pruned
Gig0/1      1,2,3,4,5```
