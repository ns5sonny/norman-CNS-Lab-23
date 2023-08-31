## Homework 1
1/c Charles Norman

Computer and Network Security

30SEP23

## Automated Webserver Creation
I followed the tutorial on [Vagrant.com](https://developer.hashicorp.com/vagrant/tutorials/networking-provisioning-operations/getting-started-provisioning) to complete this section of the homework.
I initially failed to get Apache running on my box, until I realized that the changes I was making to the Vagrantfile wouldn't take hold until I reloaded vagrant.
The next issue I ran into was loading the index.html file from the commandline in my box, but that was solved by moving the html folder into the same folder as my Vagrantfile (a step the tutorial does not specify!).
Once I was able to curl the index.html file, I added the Homework_1.html file. wget displayed the text properly, as seen below:

![cmdline.png](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%201/cmdline.png)


## Configure Networking
This section of the homework was completed with fewer hitches. I added the required lines to my Vagrantfile (this time reloading before I tried to confirm the changes). 
Pointing my browser to the appropriate path resulted in the webpage displaying on my host machine, as seen below:

![browser.png](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%201/browser.png)


## Salt Provisioning
The Vagrant [Salt](https://developer.hashicorp.com/vagrant/docs/provisioning/salt) provisioner is a provisioner that uses [YAML](https://yaml.org/spec/1.2.2/) documents to describe the required state of the machine. This includes adjustments such as installing packages, running services, and contents of particular files. Salt uses profile files (ex. `/etc/salt/cloud.profiles.d`) for each machine that has Salt installed, which allows for multiple machines to be booted at once by a host, creating a "Salt-cloud". The booted machine is referred to as a "minion" in Salt terminology. 

One bonus of using Salt is that it is already built in to Vagrant. A difference in using Salt as opposed to other provisioners is that it uses commands to install and provision a salt minion, so provisioning Salt through the Vagrantfile is **not** recommended. 

## Copying files using File provisioner
Adding the required line to the Vagrantfile was relatively straightforward, I had to use to absolute path for the Windows host machine but used a relative path for the vagrant guest. I also had to switch the backslashes to forward slashes for the source target to work properly. The part I struggled with was getting the file to actually copy correctly, until I found out I had to issue the command `vagrant provision` instead of just `vagrant reload` to get the Vagrantfile to execute the File provision. The final copy can be seen below:

![proofofcopy.png](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%201/ProofOfCopy.png)
