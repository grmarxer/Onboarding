(Previous Step: [Case Study 4 - LTM VIPs and Pools](https://github.com/grmarxer/Onboarding/blob/master/Case_Study_4-VIPs_and_Pools.md))  
<br/>  

## Case Study 5 - BIG-IP DNS  

<br/>  

### Summary  

  


<br/>  

** Add this to your existing Case Study 2 environment  
** Be able to walk me through the process of DNS recursion from a client’s (PC) perspective.  

1.	Setup a DNS server on a new VM instance (windows server or linux)  

2.	Create a GTM/DNS instance 
    - GTM has a public interface where it gets DNS requests and a private interface which leads to the backend DNS server  
    - Configure a WIP on GTM that points to one of your existing www servers.    
    - Configure the GTM listener.  What is the role and significance of the listener from  the clients perspective?  
    - Configure a DNS entry on the DNS server for the other www server that is not a WIP in GTM  
    - At least one www server must sit behind a LTM the other can just be a generic server.  
        - What is the difference between adding a generic server and a LTM?  
    - Using DIG test the WIP and the DNS server for the FQDN's configured.  Did the correct device answer the request?  Modify the TTL.  What does the TTL do?  
    - Add the second www server to the WIP.  Play with the options available for distributing traffic to the two different servers.  Round robin and Topology are the two most common  
        - Add the topology DB to GTM/DNS
        - Modify TTL’s to see how that impacts your client’s recursion.
        - What happens when the server you are testing to from your devices DNS cache goes down?  Do you immediately connect to the other www server?  

3.	Review the various WIP settings, understand where health monitors are set and why  
    - In how many places can you put a monitor on GTM?  Where does it make the most sense for your environment?  What scenarios can you think of why you would set the monitors at different levels?  Would you use different monitors at each level?  

4.	What's the difference between adding a generic server and calling out LTM?  

5.	Create a number of bogus records in your DNS server  

6.	Configure DNS Express on GTM and import the DNS servers records into GTM.  
    - What is DNS express, how does it work, why is it valuable?  

7.	Using DIG test DNS Express.  Who is returning the A record?  How do you know?  

8.	Create a second GTM/DNS device. New public interface but use the same back end internal network as the first GTM.  

9.	Create a sync group between the two GTMs  

10.	Configure a WIP to return a CNAME rather than an A or AAAA record for a FQDN.  What is a cname, when would that be useful?  
    - What types of DNS records does GTM support?  What are there uses?  
    - For extra credit create a sub domain.  Ex.  Ask for lab.com, have GTM return a cname which is student.lab.com.  Have student.lab.com pass through GTM to your backend DNS server and respond with one of your www server’s IP’s  

11.	Configure GTM to resolve and cache.  
    - Run tests from either your DNS server or another client using GTM as the DNS server.   
        - Use DIG to look up FQDN's.  
    - Where is the cache stored in GTM? Can you see the records? When do they expire?  What is the process of recursion?  
    - What is the advantage of having BIG-IP resolve and cache?  
