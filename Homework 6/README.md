## Homework 6
1/c Charles Norman

Computer and Network Security

19OCT23

## Splunk Training: Intro to Enterprise Security
The Splunk Enterprise Security (ES) feature comes installed on all Splunk servers and acts as a baseline security measure for the hosts that forward information to the server. The lesson went into fair depth on the avenues attackers use to gain access to a system, specifically pointing at Advanced Persistent Threats as examples of dangers to an enterprise network. The lesson also explained that data models are used to convert raw data into the Common Information Model (CIM) that Splunk uses to map and normalize events. Data model acceleration then helps aggregation and analysis occur faster, lending better insight to security events. The ES framework is touted as a strong method to protect against attacks, but under closer examination it is more of just an alert tool to notify network administrators when anomalous behavior is identified. For the amount of time that was spent explaining how ES can improve your network security, I honestly expected a more proactive stance than just creating graphs and generating alerts. ES requires the person responding to the incident (whether an administrator or analyst) to follow the rabbit hole to determine where the threat originated. It is then the responsibility of the analyst/admin to decide next steps, such as isolating a particular node or changing security settings to lock out attackers. 

## Windows Event Exclusion
I selected the Windows event with code 4672, which is a logon with special privileges. This occurs every time we logon, so it was excluded since it is easy to see when we got the formatting correct. It is almost always accompanied by Windows event 4624 since that event is a standard logon (it logs both when a user with elevated priveleges logs on).

## Configuration Screenshot
![input.conf](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%206/inputsconf.png)
