## Homework 3
1/c Charles Norman

Computer and Network Security

14SEP23

## Installing New Linux Distribution
Installing a separate Linux distribution turned out to be the most difficut part of this homework for me. At first I saw that a new distro was needed to receive max credit on this assignment, and given the options I decided on Oracle Linux. Unfortunately, I started the install before reading the notes, so I installed Oracle Linux 9.2 and SCC, only to discover that SCC does not have a version for Oracle Linux 9+ despite having a download for it. So I tried with Oracle Linux 8.8 and 8.7 only to encounter fatal errors from VirtualBox on both. Ultimately I used vagrant to spin up a RHEL8 VM (twice, since the first time I mis-installed SCC and had to destroy the VM to start over).

## Using SCC
Once I had the VM running properly, using SCC was fairly straightforward. I downloaded the .zip file from the Cyber Exchange site to my host machine, then issued the command `vagrant upload C:\Users\normanc\hw3\scc-5.7.2_rhel8_x86_64\scc-5.7.2_rhel8_x86_64.tar.gz /home/vagrant/hw3/scc-5.7.2_rhel8_x86_64.tar.gz` on my host machine to upload the tar.gz file to my VM. Once in the machine, I unpacked the tar.gz file and adjusted the benchmarks to only run those related to RHEL8. Once the tests finished running I extracted the resultant directory from my VM by using the command `vagrant scp :/home/vagrant/SCC C:\Users\normanc\hw3` (I had previously installed scp on my vagrant instance for this exact purpose).

## Outcomes
The first thing I saw as SCC completed was the score it assigned my VM, which was not encouraging (seen in the screenshot of SCC running below). The overall score was 38.53% [RED], 89 passed controls, 142 failed, and 143 not checked with 6 failed CAT I's. A fair amount of work would need to be put into this VM to bring it up to standard. 

![image.png](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%203/image.png)
