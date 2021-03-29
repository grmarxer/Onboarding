(Previous Step: [Case Study 5 - BIG-IP DNS](https://github.com/grmarxer/Onboarding/blob/master/Case_Study_5-BIG-IP_DNS.md))  
<br/>  

## Case Study 7 - Routing 

### Summary  

In this case study we use static routes and various catchall wildcard VIPs to route traffic from client 1 to client 2, and then from client 2 to client 1.  The purpose of this case study is to get a better understanding of static routes and routing as well as the different matching criteria for LTM VIPs  

<br/>  

### Lab Reference Architecture  

![Case Study Routing Lab Diagram](https://github.com/grmarxer/Onboarding/blob/master/diagrams/case_study_routing.png)  

<br/>  


No default routes can be used for routing traffic from client 1 to client2 or client 2 to client 1
Each client will have two interfaces in addition to the their management interface.
Client 1 NIC1 will ping Client 2 NIC1  
Client 2 NIC2 will ping Client 1 NIC2
Client 1 NIC1 will not be able to ping Client 2 NIC2