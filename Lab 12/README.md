## Lab 12
1/c Charles Norman

Computer and Network Security

16NOV23

## Installation
### Atomic Red Team

As detailed in the screenshot below, I utilized the PowerShell module to download and install Atomic Red Team on my NUC.

![Atomic PowerShell Download]()

### MITRE Caldera
The following screenshot demonstrates the working Caldera web interface. I had installed Caldera on my Kali VM and did most of the access work directly from my NUC.

![Caldera Web]()

## Caldera CTF
This screenshot shows the completed task of creating a local agent.

![Caldera Local Agent]()

This screenshot shows the completed task of creating a remote agent (I also have a deprecated local agent displayed in the agents page).

![Caldera Remote Agent]()

This screenshot shows the completed task of creating an adversary.

![Caldera Adversary]()

This screenshot shows the completed task of creating an operation.

![Caldera Operation]()

## MITRE ATT&CK Tactics
I leveraged several basic attack techniques for this section. As I discussed with LT Quarry during the lab period, I was somewhat concerned with the series of operations. I tested several of the tactics I was originally considering and found they had pre-requisites of more developed attacks. As a result, I chose tactics that could provide the baseline for a more evolved attack as well as serve as a proof-of-concept. The following screenshot demonstrates my use of the Caldera adversary to effectively complete all three tactics, then I will go into detail for each tactic with a screenshot of the tactic being used in the Atomic Red Team framework.

![IOC Caldera]()

### T1059.001: Command and Scripting Interpreter: Powershell
This tactic essentially proves that the attacker is capable of executing arbitrary commands via PowerShell. MITRE lists several well-known APT and attacks as reasons to be concerned about this specific tactic, referencing the 2016 Ukraine Electric Power Attack as a prime example.

![ART Execute PowerShell]()

### T1057: Process Discovery
This tactic allows the attacker to determine what processes are currently running on the targeted machine. MITRE notes that this tactic is useful for follow-on action, whether trying to "hide" with standard processes or causing distracting issues by killing particular processes.

![ART PowerShell Processes]()

### T1115: Clipboard Data
This tactic allows the attacker to collect data the user has stored in the Clipboard from copying information within or between applications. MITRE notes that this tactic can be used to monitor user activity or as a first step to data manipulation by then replacing user data with attacker data.

![ART Clipboard]()

## Indicators of Compromise
The first indicator of compromise I found was the "Success" icon next to each attack in the Caldera framework. Having attempted quite a few other tactics trying to find an appropriate one to use, I became very familiar with the annoying red "Failed" circle that denotes an inability to compromise the system using that particular tactic. One issue I had with the Caldera framework was the inability to select agents to execute the operation one at a time, which resulted in the failed tactic in the first row since the tactics were focused on the Windows agents rather than the Linux Agent.

![IOC Caldera]()

The second IOC I found was the list of actual processes running on 1/c Bagirov's machine. This could be leveraged to disrupt his workflow if I had decided to use my arbitrary code execution to terminate random processes.

![IOC Baggy Processes]()
