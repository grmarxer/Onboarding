## Case Study 1 - Fundamentals  

<br/>    

### Summary  

In this case study we will review basic networking, build out the students VM environment, and launch two Virtual Machines.  


<br/>  

__Note:__  Before proceeding from one step to the next the student should be able to explain, articulate, and configure everything within that step without assistance from the mentor  

__Note:__ ESXi is the hypervisor used in this example

<br/>  

## Understanding your home network  


1. Diagram your home network, include connectivity (wired and wireless) and include the cable modem, and at least 1 PC.  
    - Include device names, IP addressing, and routes    
    - For the router include:  
        - WAN and LAN IP addressing  
        - Routes  
        - DHCP Scope    
        - Port Forwarding Rules  
        - Wireless SSID's, etc.  

2. Create a Dynamic DNS account  
    - Configure home router to support Dynamic DNS  

3. Explain Layer 1 connectivity between devices  

4. Explain IP addressing (WAN and LAN), where it comes from  
    - Develop a IP scheme and DHCP scope for your home taking into consideration your lab  

5. Explain difference between hub, bridge, and switch in relation to your home network  
    - Explain the difference between a collision domain and broadcast domain  

    - Explain VLANs and discuss how to implement them on a switch, explain how VLANs break up a physical switch into different virtual broadcast domains  

6. Explain difference between a default GW and static routes  
    - Articulate how a static route is selected over another  

7. Articulate Outbound internet traffic (rendering facebook for example), specifically;  
    - Life in the day of DNS packet (LAN to WAN) - from client cache, to ARP, to DNS response - note IP addressing and SRC/DST ports at each hop  
    - Life in the day of HTTPs packet (LAN to WAN) - from ARP to client hello - note IP addressing and SRC/DST ports at each hop  

8. Articulate Inbound internet traffic, to access lab server remotely, specifically;   
    - DNS Request/Response, for Home Router via Dynamic DNS  
    - Life in the day of a packet accessing ESXi GUI remotely --IP forwarding Rules required  
        - What other IP forwarding rules might be needed in the future?


<br/>  

## Building your Home Lab Server  


1. Document server (ethernet ports, mgmt ports, RAM, Disk, Raid controller)  

    - Determine if the server has iDRAC or another remote management console  
    - Understand the difference between the server's management port and ethernet ports  

2. Determine what versions of ESXi are compatible with the server  

    - Understand difference between Type 1 and 2 hypervisors (Type 1 ESXi, Type 2 KVM)  

3. Configure RAID and Virtual Drive  
    - Discuss different RAID options and the best choice for this server  
    - Discuss what a virtual drive is and why it is needed  

4. Download the latest version of ESXi compatible with this server  

5. Install and configure the hypervisor  

    - Configure management IP, DNS, and NTP  
    - Build out six port-groups/vswitches  
        - ensure the default vmnetwork port-group is attached to the physical adapter connecting to the home network.  This will be used for management connectivity to the different vm instances/guests  
        - Develop IP addressing scheme for server port-group/vswitch networks  

6. Review what a vswitch is and how it is different/similar to a physical switch  

<br/>   

## Launch Two Virtual Machine Instances  

__Note:__ Each instance should be configured to talk to each other over all network interfaces  

1. Create one Centos and one Ubuntu virtual machine  

2. Download the DVD image  

3. Create the virtual machine  
    - select appropriate disk/RAM/CPU
    - Configure with two interfaces
        - Attach interfaces to appropriate port-group/vswitch  

4.  Walk user through installer  
    - Configure IPv4 for each interface  
    - Install SSH Server  

5.  User should configure instance in CLI only  

6.  Perform an OS update/upgrade  

7.  Disable firewall and SElinux   

8.  Configure NTP and verify  

9.  Using tcpdump verify connectivity over each interface  
    - [An introduction to using tcpdump at the Linux command line](https://opensource.com/article/18/10/introduction-tcpdump)  
    - [Man page of TCPDUMP](https://www.tcpdump.org/manpages/tcpdump.1.html)  
        - Have the student ping between instances and verify connectivity in the tcpdump beginning with the ARP  
        - Review ARP table  

10.  Have student change the vswitch attached to the non management interfaces and note results  

11.  Have the student modify the non-management interface IP addresses using the CLI  
        - Verify connectivity  

12. Review routing table  
    - Why is there more than one default route?  
        - What are the implications of having more than one default route  
        - Determine which default route will be used  
        - Remove incorrect default routes   

13. Add a third network interface to each instance  
    - Review the steps required to add a interface to the Ubuntu instance  
    - Review the steps required to add a interface to a Centos instance  

14.  Configure IPv4 on the new interface using the command line  
        - Verify connectivity between instances over this interface  
        - Review the routing table  
            - Did it change?  
            - Are the routes correct?  


<br/>  

## Reinforce Previous Learning  

__Note:__ Student should complete this step completely on their own  

- Completely wipeout the lab server configuration, reinstall the hypervisor (ESXi) and complete the steps above again  

 
<br/>  

### Next step  

[Case Study 2 - Introduction to F5 Documentation and Product Information](https://github.com/grmarxer/Onboarding/blob/master/Case_Study_2-F5_Documentation_and_Product_Information.md)  

<br/>  
<br/>  
<br/>
-----------------------------------------------------------------------  

### backup notes  

ip address best practices  
naming best practices  
Configure IPv4 and Ipv6  

