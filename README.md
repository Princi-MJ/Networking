# Networking
## Cisco Router and Switch Basics
##### The main things leearned from this lab are as follows 

 
 * the switch can have connectivity to other ip subnet once the ip is set using the following commanc
 * on config terminal (ip default-gateway and then ip address where you want to sent traffic to)
 * Interface details can be seen when this command is run on enable privildge (show interface f0/1)
 * the above command shouldn't be confused with this one (show ip interface brief ) where you see details of the list of all interface connected on the device
 * when setting the speed of the interface go into the interface at conf t priviledge and then set the speed or dublex. this has to be done on both end of the links
 * So this command (show cdp neighbors) shows the neighbors directly attached to the devices, you can disable it on the interface by going to the interface and disabling it (int f0/0 and then no cdp enable) that will prevent the device on the end of that interface to not recieve network information
