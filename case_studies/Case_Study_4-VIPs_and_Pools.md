(Previous Step: [Case Study 3 - Instantiate Two BIG-IP's and put them in a HA Pair](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_3-BIG-IP_HA_Pair.md))  
<br/>  

## Case Study 4 - LTM VIPs and Pools  


### Summary  

In this case study we will create several LTM VIPs and demonstrate load balancing within the ESXi environment using one linux client and two linux servers.  We also introduce route domains.  

After completion the student should have a good understanding how each VIP works architecturally and where to apply them in a customer environment.  


<br/>  

### Create three Linux instances (one client and two servers)  

__Note:__ If you have already instantiated linux boxes in the previous section you can reuse those.  

1. Build two linux boxes to be used as servers (centos or ubuntu)  
    - Two NICs  
        - one mgmt. (home network) 
        - one on the internal network  
    - Configure NTP, disable SELinux, disable firewall  
    - Load apache or another webserver and configure a custom web page.  
        - Web page ex.  “It works, you reach linux box 1”  

2. Build one linux box to be used as the client (centos or ubuntu)  
    - Two NICs  
        - one mgmt. (home network) 
        - one on the external network  
    - Configure NTP, disable SELinux, disable firewall  
    - Use CURL for HTTP/S test cases

<br/>  


### Create the following VIPs  

__Helpful Links__  
   - [K55185917: Overview of BIG-IP virtual server types (12.x - 15.x)](https://support.f5.com/csp/article/K55185917)  
   - [K8082: Overview of TCP connection setup for BIG-IP LTM virtual server types](https://support.f5.com/csp/article/K8082)   
   - [K411: Overview of packet tracing with the tcpdump utility](https://support.f5.com/csp/article/K411)  
   - [K40033505: Explaining the output of tmsh show sys connection](https://support.f5.com/csp/article/K40033505)  
   - [K53851362: Displaying and deleting BIG-IP connection table entries from the command line](https://support.f5.com/csp/article/K53851362)  

<br/>  

__Note:__ We will use this case study to become familiar with the BIG-IP connection table.  The BIG-IP connection table contains information about all the sessions that are currently established on BIG-IP system.  After successfully passing traffic through each VIP below, review the connection table and identify the VIP specific entries.  

<br/>  


#### HTTP (Port 8080)  
- Full proxy  
- Keep source address  
- Use priority groups to LB to one server only until it is down.  
- HTTP Monitor with GET defined  
- Assign two monitors to the pool and only fail when both monitors are down  

#### HTTPS (Port 8081)
- Full proxy  
- SSL Offload (create a certificate)  
- SNAT (automap)  
- Push client src address to the server in a HTTP header  
- Round robin  
- HTTP Monitor without GET defined  


#### SSH (Port 22)  
- Full proxy  
- No SNAT  
- Round Robin  
- TCP half-open Monitor  

#### Wildcard listener (0.0.0.0/0)  
- Layer 4 only
- No SNAT
- No pool
- Change the default GW on a specific node to something other than the BIG-IP and curl that specific node's IP from your client.  What happens and why?  Document findings using TCPDUMP.  

#### Route Domains   
- Create route domain 10  
- Copy the HTTP (port 8080) VIP above and put it in this route domain  
- Attach it to the same pool as the VIP above (Pool to remain in RD 0)  
- Use the same IP addressing (VIP should have same IP as the VIP above)  
- Make the necessary modifications to Interfaces, VLANs, Self-IP’s etc to support RD 10  


<br/>  

### Discussion items to reinforce learning  

- Articulate the TCP three-way handshake for a Full proxy VIP?  Use TCPDUMP to reinforce findings  
- Articulate the TCP three-way handshake for a FASTL4 VIP? Use TCPDUMP to reinforce findings  
- Articulate SNAT and where SNAT addresses get assigned? And in what order?  
- Articulate the different profiles assigned to each VIP and why?  
- Articulate Address/port translation settings on VIP (advanced config)?  
- Articulate MAC Masquerade and its significance?  
- Articulate three-way handshake to a full proxy VIP when pool is down?  
- Can you ping a full proxy VIP when the pool is down?  Articulate findings.  
- What happens with the SSH VIP when you get load balanced to the second node?  Why did it fail?  
- Why is it important to have the GET defined in a HTTP monitor?  
- Look at the BIG-IP connection table.  Articulate what you see (#tmsh show sys connection)  

<br/>  

### Next step  

[Case Study 5 - Routing](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_5-Routing.md)  