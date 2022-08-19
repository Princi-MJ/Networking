# Networking

## 13 The Cisco Troubleshooting Methodology
#### What i learned form this Lab

 * Steps to take when troubleshooting an issue with networking
 * Questions to ask to guide you in finding a solution 
     * Was it working before? if so, has something changed which could cause the problem? this will usually direct you to the cause
     * Is the problem affecting evrybody or just one particular user? if its affecting just one users, the likelihood is that the problem is at their end
 * one important command in this lab was ip name-server **address** this is used to set the dns server address so router know where it is located.
 * other important command ofcourse are ping, traceroute, and telnet. these are all used for troubleshooting an issue.
 * depending on what the issue is, the commands to use to troubleshoot will be a bit different.
 
 ## 14 Cisco Router and Switch Basics
##### The main things leearned from this lab are as follows 

 
 * the switch can have connectivity to other ip subnet once the ip is set using the following commanc
 * on config terminal (ip default-gateway and then ip address where you want to sent traffic to)
 * Interface details can be seen when this command is run on enable privildge (show interface f0/1)
 * the above command shouldn't be confused with this one (show ip interface brief ) where you see details of the list of all interface connected on the device
 * when setting the speed of the interface go into the interface at conf t priviledge and then set the speed or dublex. this has to be done on both end of the links
 * So this command (show cdp neighbors) shows the neighbors directly attached to the devices, you can disable it on the interface by going to the interface and disabling it (int f0/0 and then no cdp enable) that will prevent the device on the end of that interface to not recieve network information
 
 
 ## 14 Cisco Device Management
##### The main things leearned from this lab are as follows 

* write erase command will do factory reset
* Changing the boot order of the router and reloading the router, so this is like pointing the router to boot a different image and then reload from that image while still in the running configuration you can copy and making the running conf into start.

![image](https://user-images.githubusercontent.com/110028539/184810228-83abbc8e-da4e-44c9-bccf-d62d6a6468d4.png)

* configuring of the backup e.g running config saving them on the router or server like tftp.
* backing up the OS image on the router and upgrading as well
![image](https://user-images.githubusercontent.com/110028539/184810569-6d6a4298-465b-4616-b9c8-1d7a911c975d.png)

## 16 Routing Fundamentals (Part A)
#### Routing is super important
* knowing when to use static route and summary routes very crutial
* in Part 2, will be doing longest prefix and load balancing whhich is also crutial in networking
* the code here i was familir with hence it was just walk in the park

## 16 Routing Fundamentals (Part B)
#### Routing is super important
![image](https://user-images.githubusercontent.com/110028539/185545354-2f1c5e81-7dae-45dd-b006-1e33bf6b01e1.png)
* as you can see from the above image, i have configured the default routes to the internet 
* and load balancing also configured to avoid traffic taking the long route when they can simply go through R5
* Same with the longest prefix, thats also configured in this part B

## 17 Dynamic routing fundamentals

* routing protocols are more scalable than the admni static routes
* stating roautes only feasible for very small envirnment
* there many dynamic routing protocols and below are some of them

### RIP (Routing Information Protocol)
* version is the latest one
* its the easiest and simplest routing protocol
* ist configured like this
	**
	router rip
	version 2
	network 10.0.0.0
	no auto-summary
	**
* RIP uses a hop count as a metric
* RIP administrative distance is 120
* RIP is a distance vector routing protocol, all it knows is what its directly connected neighbors and the list of networks advirtised by them
* CLI command for checking state of all links is 
	* show ip rip database

### OSPF (Open Shortest Path First)
* ospf is the most famous, it selects the best route by making use of the cost as a metric
* it can however be complex and difficult as it can scale to any size of the network
	**
	router ospf 1
	network 10.0.0.0 0.255.255.255 area 0
	**
* OSPF is a link state protocol, so it knows the state of every link on the router
* CLI command for checking state of all links is 
	* show ip ospf database
* OSPF administrative distance is 110

### EIGRP (Enhanced Interior Gateway Routing Protocol)
* it is considered as a proprietary of cisco
* configuration of eigrp is as follows
	**
	router eigrp 100
	no auto-summary 
	network 10.0.0.0 0.255.255.255
	**
* Eigrp administrative distance is 90
* Eigrp also used a metric that takes into consideration of bandwidth and delay

** These are the dynamic routing procols covered in this lab, there is many more which will be done in the future such as IS-IS **

* Floatng static routes are used as backup routes
* they are configured in this manor ip route 10.0.0.0 255.255.255.0 10.0.2.1 95
* the above static floating route would work if the eigrp route went down, as it will now become the best route given the lower AD comparing to OSPF (110) and RIP (120)



 
       
