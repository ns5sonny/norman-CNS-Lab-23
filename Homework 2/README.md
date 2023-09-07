## Homework 2
1/c Charles Norman

Computer and Network Security

06SEP23
## Updating .yml File
I initially ran into some difficulty working with the .yml file - I copied everything directly from the Labsetup folder and made a new copy of HostA to ensure everything was working, and got a strange error when I first tried to build the containers. After a fair amount of Googling I discovered that pasting the info for the new host had messed up the formatting in a way that I couldn't see in the GNU nano editor. I used an online tool to validate the .yml file and got the containers built. The original container I picked was for some reason unable to run the bash command "ip," so I selected a different one that caught my eye and got it running.
## Exploring Docker Containers
The first container I considered when I was looking through the container list was alpine, an Alpine Linux-based container that provides lightweight access to the OS. Alpine describes itself as an "independent, non-commercial, general purpose Linux distribution designed for power users who appreciate security, simplicity and resource efficiency." Essentially, it is just another way to get the simplicity of Linux without something as large as Ubuntu. There aren't many options provided in the Docker listing, but it has a wide array of supporting links that provide information on how to leverage Alpine's features. 

The second container I considered was datacollector, a container created by Lacework as a way to track other entities deployed in the VM/related cloud. Lacework describes itself as "delivering cloud security to workloads and accounts on AWS, Azure, GCP and other public and private clouds." Lacework also provides a service that tracks behavior for anomalies, insider threats, and breaches. The Docker page has almost no information on the container and provides no options or features, so some Googling was in order. The container provides access to the majority of the Lacework features available to enterprise users, most importantly vulnerability identification for other containers. Unfortunately, I was not able to get this container working with my stack so I gave up and switched to Grafana.

## Grafana
Grafana is an open source container that provides operational dashboards for data on various stacks. Grafana claims to "unify your data, not your database" (fancy) by organizing all data available to it into a single flexible dashboard. One of the was it can be leveraged is through a stack with several other data management tools (for metrics, logs, and traces) to provide a holistic view of services rendered. This could be useful for a project in the future but it's entirely useless for me at the moment since I can't access the GUI through the console and don't have any data for it to display. As seen below, I am able to ping my hosts and log into the Grafana container (which would be how I would access the data portal if I had need of it).

![image.png](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%202/image.png)
