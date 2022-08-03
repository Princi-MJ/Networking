# Networking
## 14 Cisco Router and Switch Basics
##### The main things leearned from this lab are as follows 

 
 * the switch can have connectivity to other ip subnet once the ip is set using the following commanc
 * on config terminal (ip default-gateway and then ip address where you want to sent traffic to)
 * Interface details can be seen when this command is run on enable privildge (show interface f0/1)
 * the above command shouldn't be confused with this one (show ip interface brief ) where you see details of the list of all interface connected on the device
 * when setting the speed of the interface go into the interface at conf t priviledge and then set the speed or dublex. this has to be done on both end of the links
 * So this command (show cdp neighbors) shows the neighbors directly attached to the devices, you can disable it on the interface by going to the interface and disabling it (int f0/0 and then no cdp enable) that will prevent the device on the end of that interface to not recieve network information

## 13 The Cisco Troubleshooting Methodology
#### What i learned form this Lab

 * Steps to take when troubleshooting an issue with networking
 * Questions to ask to guide you in finding a solution 
     * Was it working before? if so, has something changed which could cause the problem? this will usually direct you to the cause
     * Is the problem affecting evrybody or just one particular user? if its affecting just one users, the likelihood is that the problem is at their end
 * one important command in this lab was ip name-server **address** this is used to set the dns server address so router know where it is located.
 * other important command ofcourse are ping, traceroute, and telnet. these are all used for troubleshooting an issue.
 * depending on what the issue is, the commands to use to troubleshoot will be a bit different.
       
