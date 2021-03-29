
## Case Study 7 - Routing 

### Summary  

In this case study we use static routes and various catchall wildcard VIPs to route traffic from client 1 to client 2, and then from client 2 to client 1.  The purpose of this case study is to get a better understanding of static routes and routing as well as the different matching criteria for LTM VIPs  

<br/>  

### Lab Reference Architecture  
<br/>  

![Case Study Routing Lab Diagram](https://github.com/grmarxer/Onboarding/blob/master/diagrams/case_study_routing.png)  

<br/>  


### Requirements for Lab Configuration  

- Each client will have two interfaces in addition to the their management interface.  

- You must use the IP addressing outlined in the diagram.  

- Only use catchall wildcard fastl4 VIPs with no pools.  

    - A total of 5 VIPs is required for the complete solution. The VIPs on BIG-IP 1 and BIG-IP 3 must be VLAN specific.  

- No default routes can be used on either the clients or the BIG-IPs for routing traffic from client 1 to client 2 or client 2 to client 1. 

- No firewall rules can be used, all tasks must be completed in this case study using LTM only, static routes, and fastl4 VIPs

- Client 1 NIC 1 must not be able to ping Client 2 NIC 2  

- Client 1 NIC 2 must not be able to ping Client 2 NIC 2  

- Client 2 NIC 1 must not be able to ping Client 1 NIC 1    

- Client 2 NIC 2 must not be able to ping Client 1 NIC 1  

<br/>  

### This Case Study is complete when...  

- Client 1 NIC 1 can ping Client 2 NIC 2 (VLAN 1 to VLAN 2 to VLAN 3 to VLAN 4)  
- Client 2 NIC 2 can ping Client 1 NIC 2 (VLAN 5 to VLAN 3 to VLAN 2 to VLAN 6)  

__Note:__  You will be expected to use tcpdump to show that the traffic from client 1 to client 2 and from client 2 to client 1 is traversing the correct interfaces at each hop.  