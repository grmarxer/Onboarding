## F5 ASE and SE Onboarding

### Overview  

This guide was developed to help onboard both ASE's and SE's into F5 and designed to fill in the 'gaps' from any previous F5 training the student has received.  The student should not attempt a case study specific to BIG-IP or a BIG-IP module until they have attended the F5 instructor led training on the subject.  
  

### There are seven case studies in this guide:  

##### Case Study 1 - Fundamentals  
##### Case Study 2 - F5 Documentation and Product Information  
##### Case Study 3 - Instantiate Two BIG-IP's and put them in a HA Pair  
##### Case Study 4 - LTM VIPs and Pools  
##### Case Study 5 - Routing  
##### Case Study 6 - BIG-IP DNS  
##### Case Study 7 - AFM  

<br/>  

- The student should complete "ADMINISTERING BIG-IP and CONFIGURING BIG-IP LTM: LOCAL TRAFFIC MANAGER" prior to starting case study 3 and 4.  
- The student should complete "CONFIGURING BIG-IP DNS (FORMERLY GTM)" prior to starting case study 5.  
- The student should complete "CONFIGURING BIG-IP AFM: ADVANCED FIREWALL MANAGER" prior to starting case study 6.  
<br/>  

__Note:__ Each case study above builds off the one before it, thus a student attempting to start at case study 4 will struggle as the components necessary for case study 4 were built in case studies one through three.  

<br/>  

__Case Study 1 - Fundamentals__ This case study helps educate the student on general networking and server OS/VM basics. It uses repetition to reinforce learning and requires the most support from the mentor.  There are several sections in this case study and it is critical that the student not move forward until the current topic can be explained in detail.  The networking section of this case study uses the students home network as the reference architecture.   It is expected that the mentor will need to walk the student through each section of this case study doing a majority of the configuration with the student.  Once first pass is completed, the student is then expected to destroy the contents of this case study and redo it completely on their own.    

__Case Study 2 - F5 Documentation and Product Information__  In addition to hands on learning, it is critical that the student learn how to navigate the F5 documentation and tools they will use to support their customers.  This includes support.f5.com, knowledge articles, DevCentral, tron, pre-sales cases, licensing, iHealth, etc.  

__Case Study 3 through 6__ builds on top of the F5 instructor led learning; having the student configure, explain, and articulate the components of each case study.  Success is not determined by configuring a VIP and having it go green, success is determined by articulating how a standard VIP TCP handshake completes (client side and server side) using TCPDUMP, why the pool is green, how a pool member is selected and session persistence occurs.  Each case study is designed to teach the student the basic building blocks of BIG-IP, in detail, and how each of those building blocks works from a TCPDUMP/tmos connection table perspective. These case studies should require less mentor support as the student should already have a general understanding from the instructor led training.  At the end of each of these case studies the mentor will work with the student to reinforce the learning by having the student articulate the "how and why" in detail.  

__Case Study 7 - Routing__  Was built to help students new to static routing.  It also reinforces VIP learning from the LTM Instructor led course.  This case study can be completed anytime after completing the LTM instructor led course.

<br/>  

### Recommended Software tools in Addition to the Standard F5 IT Build

-	Wireshark with F5 plugin enabled  
-	Putty/mputty  
-	Notepad++  
-	SCP file transfer tool (winscp - windows, cyberduck -mac)  
-	iRule Editor  
-	ireasoning mib browser  
-	postman  

<br/>  

### Prerequisites  

1. Home server capable of running ESXi or KVM
2. Complete the F5 instructor led training prior to attempting a particular case study


<br/>  

----

### Case Studies  

[Case Study 1 - Fundamentals](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_1-Fundamentals.md)  

[Case Study 2 - Introduction to F5 Documentation and Product Information](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_2-F5_Documentation_and_Product_Information.md)  

[Case Study 3 - Instantiate Two BIG-IP's and put them in a HA Pair](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_3-BIG-IP_HA_Pair.md)  

[Case Study 4 - LTM VIPs and Pools](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_4-VIPs_and_Pools.md)  

[Case Study 5 - Routing](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_5-Routing.md)  

[Case Study 6 - BIG-IP DNS](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_6-BIG-IP_DNS.md)  

[Case Study 7 - AFM](https://github.com/grmarxer/Onboarding/blob/master/case_studies/Case_Study_7-AFM.md)  








