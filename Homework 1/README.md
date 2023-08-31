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
