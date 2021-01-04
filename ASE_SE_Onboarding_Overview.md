## F5 ASE and SE Onboarding

<br/>  

### Overview  

This guide was developed to help onboard both ASE's and SE's into F5 and designed to fill in the 'gaps' from any previous F5 training the student has received.  The student should not attempt a case study specific to BIG-IP or a BIG-IP module until they have attended the F5 instructor led training on the subject.  

#### There are five case studies in this guide:  

##### Case Study 1 - Fundamentals  
##### Case Study 2 - F5 Documentation and Product Information  
##### Case Study 3 - Instantiate Two BIG-IP's and put them in a HA Pair  
##### Case Study 4 - LTM VIPs and Pools  
##### Case Study 5 - BIG-IP DNS  
##### Case Study 6 - AFM  

<br/>  

- The student should complete "ADMINISTERING BIG-IP and CONFIGURING BIG-IP LTM: LOCAL TRAFFIC MANAGER" prior to starting case study 3 and 4.  
- The student should complete "CONFIGURING BIG-IP DNS (FORMERLY GTM)" prior to starting case study 5.  
- The student should complete "CONFIGURING BIG-IP AFM: ADVANCED FIREWALL MANAGER" prior to starting case study 6.  
<br/>  

__Note:__ Each case study above builds off the one before it, thus a student attempting to start at case study 4 will struggle as the components necessary for case study 4 were built in case studies one through three.  

<br/>  

__Case Study 1 - Fundamentals__ This case study helps educate the student on general networking and server OS/VM basics. It uses repetition to reinforce learning and requires the most support from the mentor.  In this case study there are several sections and it is critical that the student not move on from one section to the next until the current topic can be explained in detail.  The networking section of this case study uses the students home network as the reference architecture.   It is expected that the mentor will need to walk the student through each section of this case study doing a majority of the configuration with the student.  Once first pass is completed with the student, the student is then expected to destroy the contents of this case study and redo it completely on their own.    

__Case Study 2 - F5 Documentation and Product Information__  In addition to the hands on learning it is critical the student learn how to use and navigate the F5 documentation and tools that they will need to support their customers.  This includes support.f5.com, knowledge articles, DevCentral, tron, pre-sales cases, licensing, iHealth, etc.  

__Case Study 3 through 6__ builds on the F5 instructor led learning having the student configure, explain, and articulate the components of each case study.  For example success is not determined by configuring a VIP and having it go green, success is determined by the student articulating how a standard VIP TCP handshake completes (client side and server side), proving with TCPDUMP why a pool is green and how a pool member is selected and session persistence occurs.  Each case study is designed to make the student understand the basic building blocks of BIG-IP in detail and how each of those building blocks works from a TCPDUMP/tmos connection table perspective. These case studies should require less mentor support as the student should already have a general understanding from the instructor led training.  At the end of each of these case studies the mentor will work with the student to reinforce the learning by having the student articulate the "how and why" in detail.


<br/>  

### Prerequisites  

1. Home server capable of running ESXi or KVM
2. Complete the F5 instructor led training prior to attempting a particular case study


<br/>  

### Next step  

[Case Study 1 - Fundamentals](https://github.com/grmarxer/Onboarding/blob/master/Case_Study_1-Fundamentals.md)  








