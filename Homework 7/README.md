## Homework 7
1/c Charles Norman

Computer and Network Security

26OCT23

## VNC Exploit
VNC (Virtual Network Computing) is a remote GUI desktop-sharing service that allows users to control a separate computer. I specifically chose this exploit since I noticed the service available on the Metasploit box from the last lab and had no idea what it was. I Googled it briefly and found it mildly interesting, especially since it can be leveraged to provide a GUI instead of just console access. VNC uses the RFB (Remote Framebuffer) protocol, another item with which I was unfamiliar. Searching exploit-db revealed the following: https://www.exploit-db.com/exploits/37598 which, although it doesn't contain much detail on the exploit, shows the full code the exploit uses. Reading through it, the exploit assumes we either already have the password or the VNC session is unathenticated. There is a scanner in Metasploit to determine the password which could be good to use in either case to get practice. Once connected, the exploit opens an xterm window and delivers the assigned payload (most likely a reverse shell or some other type of malware). One interesting feature for this specific exploit is its flexibility: it can be leveraged on either Windows or Linux since the exploit is coded to handle either situation automatically.  

## Instructor Approval
Instructor approval for use of this exploit was granted at 1340 on 24OCT23 by LT Quarry.

## CWE/CVE
There is no related CWE or CVE for this exploit. Metasploit provided the following information as to why that is the case: "There are multiple reasons why this might happen:
- The vendor does not wish to assign a CVE.
- There is a delay in the process of assigning a CVE.
- The module is not meant to target a specific CVE. Likely something generic.
- We are unable to find a matching CVE because there isn’t enough technical information to verify."

In my personal opinion I believe the third option is the most likely reason why there is no CVE associated with this exploit. VNC is available on both Windows and Linux, meaning any CVE assigned to it would have to be rather broad, which is not something we want to see in a CVE.
