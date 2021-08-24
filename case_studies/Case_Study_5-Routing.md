
(Previous Step: [Case Study 4 - LTM VIPs and Pools](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_4-VIPs_and_Pools.md))  
<br/>  

## Case Study 5 - Routing 

### Summary  

In this case study we use static routes and various catchall wildcard VIPs to route traffic from client 1 to client 2.  The purpose of this case study is to get a better understanding of static routes/routing as well as the different matching criteria for LTM VIPs  

<br/>  

### Lab Reference Architecture  
<br/>  

![Case Study Routing Lab Diagram](https://github.com/grmarxer/Onboarding/blob/master/diagrams/CaseStudy_routing_p1.png)  

<br/>  


### Requirements for Lab Configuration  

- You must use the IP addressing outlined in the diagram.  

- Only use catchall wildcard fastl4 VIPs with no pools.  
    - Use the minimum number of VIPs possible to complete the solution.  
    - The VIPs on BIG-IP 1 and BIG-IP 3 must be VLAN specific.  

- No SNAT  

- No default routes can be used on either the clients or the BIG-IPs for routing traffic from client 1 to client 2

- No firewall rules can be used, all tasks must be completed in this case study using LTM only, static routes, and fastl4 VIPs

- Client 2 NIC 1 must not be able to ping Client 1 NIC 1    

<br/>  

### This Case Study is complete when...  

- Client 1 NIC 1 can ping Client 2 NIC 1 (VLAN 1 to VLAN 2 to VLAN 3 to VLAN 4)  

__Note:__  You will be expected to use tcpdump to show the traffic traversing each interface (request/reply) from client 1 to client 2.  

<br/> 

### Next step  

[Case Study 6 - BIG-IP DNS](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_6-BIG-IP_DNS.md)  