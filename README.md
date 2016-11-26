# Volatillity Plugin - Carve Network Packets

A plugin which can carve network packets out of a memory dump and then do a quick analysis of the packets, for potentially identifying malicious traffic quickly and getting a quick overview of how the network looks like for the analyzed system.

The plugin will generate output below and dump a pcap with carved packets.

```
Example output:

vol.py --plugins=/tmp/plugin/ -f memdump.mem --profile=WinXPSP2x86 networkpackets --dump-dir=result_folder/

Volatility Foundation Volatility Framework 2.5

Network analysis of carved packets:

Number of carved packets
------------------------
625                     


Potential local interfaces used by analyzed system
--------------------------------------------------
172.16.237.134 <-> 00:0d:20:1f:c2:b4              


Potential gateways used by analyzed system
------------------------------------------
172.16.237.224 <-> 00:0d:20:1e:c1:b2      
No ARP resolves <-> 00:50:56:e8:a8:57     


ARP resolves                           Number of packets
-------------------------------------- -----------------
172.16.237.134 is at 00:0d:20:1f:c2:b4                 6
172.16.237.224 is at 00:0d:20:1e:c1:b2                 3


Public IP src or dst Number of packets Source ports < 1024 Destination ports < 1024  Total bytes Minimum packet size Maximum packet size Average packet size
-------------------- ----------------- ------------------- ------------------------ ------------ ------------------- ------------------- -------------------
50.4.11.25                          35                  80                                 30166                  40                1500                 861
149.80.77.59                        12                  80                                 12079                  40                1500                1006
108.132.176.126                     11                  80                                 12047                  40                1500                1095
107.55.44.71                         7                 443                                  9844                1224                1500                1406
210.70.197.200                       3                 443                                   124                  40                  44                  41
8.8.8.8                              2                  53                                   231                 112                 119                 115
```