(Previous Step: [Case Study 2 - Introduction to F5 Documentation and Product Information](https://github.com/grmarxer/Onboarding/blob/master/Case_Study_2-F5_Documentation_and_Product_Information.md))  
<br/>  

## Case Study 3 - Instantiate Two BIG-IP's and put them in a HA Pair  

### Summary  

In this Case Study you will build out two BIG-IP's and put them in a HA pair.  The reference architecture has been illustrated below, you can use this architecture or create your own (IP's and naming).  The architecture below will be used in all subsequent Case Study's for consistency.  

The student should complete this Case Study on their own using the available documentation and only reach out to the mentor with specific questions.  

Once the Case Study lab work is complete reinforce the learning using the section below as a guide.  


<br/>  

### Lab Reference Architecture  

![Case Study 1 Lab Diagram](https://github.com/grmarxer/Onboarding/blob/master/diagrams/CaseStudy1_diagram.png)  

<br/>  


### Launch Two BIG-IP VE Instances   

Determine what license to generate and why, discuss the licensing nomenclature  
  - Review and bookmark the following knowledge articles  
       - [Good, Better, Best Licensing](https://www.f5.com/pdf/licensing/good-better-best-licensing-overview.pdf)  
       - [K14810: Overview of BIG-IP VE license and throughput limits](https://support.f5.com/csp/article/K14810)  
       - [K15643: BIG-IP VE Version Plus license offerings](https://support.f5.com/csp/article/K15643)  
       - [K15831: How the BIG-IP VE system enforces the licensed throughput rate](https://support.f5.com/csp/article/K15831)  


Determine what BIG-IP Image (version and size) to use and why  
   - Explain how to navigate and the contents of https://downloads.f5.com/  
   - Review and bookmark the following knowledge articles   
       - [K14946: Overview of BIG-IP VE image sizes](https://support.f5.com/csp/article/K14946)  
       - [BIG-IP VE Supported Platforms](https://clouddocs.f5.com/cloud/public/v1/matrix.html)  
       - [K8986: F5 software lifecycle policy](https://support.f5.com/csp/article/K8986)  
       - [K5903: BIG-IP software support policy](https://support.f5.com/csp/article/K5903)  
       - [K15796: Hardware requirements to host BIG-IP VE on private cloud platforms](https://support.f5.com/csp/article/K15796)  


<br/>  

1. Use the documentation to deploy two BIG-IP ESXi instances  
    - [VMware ESXI and vCloud Director Knowledge Center](https://support.f5.com/csp/knowledge-center/cloud/Virtual%20Editions/VMware%20ESXI%20and%20vCloud%20Director)  
    - Configure 2 vcpu's/4 GB RAM  
    - Assign the correct vswitches to the BIG-IP Mgmt port and TMM interfaces 1.1-1.3  
        - Connect the BIG-IP mgmt. interface to your home network  
        - Assign TMM interfaces to the vswitches that you plan to use for internal, external, and HA

2. Use the ESXi instance console to configure the mgmt port settings  

3. License the BIG-IP, configure hostname, passwords, and timezone  

4. Configure DNS and NTP  

5. Walk through the instance settings on the ESXi host  

6. Demonstrate what you have configured on BIG-IP in both the GUI and the CLI  


<br/>  

### Configure BIG-IP Into a HA Pair  

__Helpful Links__  
   - Use the LTM documentation on [support.f5.com](https://support.f5.com) if you have questions on self-ips’ vlans’ etc.  
   - This will help with building the BIG-IP internal and external networks - [Manual : BIG-IP System: Initial Configuration](https://techdocs.f5.com/en-us/bigip-15-1-0/big-ip-system-initial-configuration.html)  
   - This link will help build the HA Pair.  [Manual : BIG-IP Device Service Clustering: Administration](https://techdocs.f5.com/en-us/bigip-14-1-0/big-ip-device-service-clustering-administration-14-1-0.html)  

<br/>  


1. Configure the 2 BIG-IP’s into a HA Pair __(Do not use the HA wizard)__  

2. The internal and external facing networks should have a floating IP between them (Traffic-group-floating)  

3. Enable MAC Masquerade on Traffic-group 1   
    - Create a unique MAC address for MAC masquerade  
        - [K3523: Choosing a unique MAC address for MAC masquerade](https://support.f5.com/csp/article/K3523)  

4.	For config sync and mirroring use the HA interface  

5.	For failover use the mgmt, HA, and Internal interface.  __Note:__ Configure network failover  

6.	Set the external self-IP port lockdown to allow none  

7.	Set the HA interface self-ip port lockdown to allow all  

8.	Set the internal interface self-ip port lockdown to allow default  

9.	Use whatever IP addressing you prefer, IP addressing in the above diagram is for example.  

10.	When working properly the sync icon will be green, and one VE will be active and the other standby  

<br/>  


### Discussion items to reinforce learning

1.	Articulate the different OVA and QCOW2 files on downloads.f5.com (1 slot, all, etc.)  

2.	Articulate the appropriate disk space required for the image you used  

3.	Articulate port lockdown settings  

4.	Articulate what config sync, mirroring, and failover settings do and how each of those functions work  

5.	Articulate the ports required for HA  

6.	Articulate what protocol is used to form the HA Pair    

7.	Demonstrate web pages created on Linux boxes using curl  

<br/>  

### Next step  

[Case Study 4 - LTM VIPs and Pools](https://github.com/grmarxer/Onboarding/blob/master/Case_Study_4-VIPs_and_Pools.md)  