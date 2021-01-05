(Previous Step: [Case Study 5 - BIG-IP DNS](https://github.com/grmarxer/Onboarding/blob/master/Case_Study_5-BIG-IP_DNS.md))  
<br/>  

## Case Study 6 - AFM 

### Summary  

In this case study the student will work with AFM creating rules in different contexts, enable logging, DDOS, and NAT.  This environment should be layered on top of the previous LTM configuration.  When complete the student should me able to walk the mentor through all of the features below and articulate the different traffic flows. 


<br/>  

1.	Demonstrate and articulate the difference between ADC mode and FW mode  

2.	Articulate BIG-IP AFM Context Hierarchy  
    - What are the different contexts  

3.	Build a policy for both Global and Virtual Server Context  
    - Configure inbound and outbound rules  
    - For traffic ingress-ing the AFM that hits a rule and passes through AFM, is a subsequent rule required for the return traffic (ex SYN sent, SYN ACK sent back) is a rule required for the SYN-ACK?   
    - Use FQDN in a Rule.  
        - How does the FQDN get translated into IP’s  
        - How are multiple IPs for the same FQDN captured?  
        - How long are the IP’s good for?  
    - Understand address lists, port lists, etc.  

4.	Configure logging profile for both the Global and VS context.  
    - Use on box logging  
    - Work through and demonstrate the different logging options  

5.	Turn on logging for default deny rule  

6.	Configure NAT Source Translation inside AFM  
    - Configure global and VS context  

7.	Put two AFM’s in a HA pair.  
    - Do specific rules need to be added?  

8.	Articulate and demonstrate the difference between Accept and Accept decisively  

9.	Build out a DDOS profile/setting you can test.  
    - Demonstrate logging  
    - auto-thresholding  
    - Articulate dynamic DOS vectors.  
        - Explain how it works  
