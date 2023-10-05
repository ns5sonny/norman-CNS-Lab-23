## Homework 5
1/c Charles Norman

Computer and Network Security

05OCT23

## Red Hat Academy

### 1. SSH to root:
   
![ssh root](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/10.2.6CN.png)

This demonstrates the ability of the root user to see what users logged in from which locations. 


### 2. SSH hostname:
   
![ssh hostname](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/10.2.12CN.png)

This demonstrates the ability of the user on `servera` to execute the `hostname` command on `serverb` remotely.

### 3. Sharing SSH keys:
   
![ssh sharing](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/10.4.4CN.png)

This demonstrates the function of sharing RSA SSH keys via `ssh-copy-id`.

### 4. Sharing secondary SSH keys:
   
![ssh secondary](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/10.4.9CN.png)

This demonstrates the function of sharing a secondary SSH key to a remote machine.

## SSH to Jump Box

Creating the keys on the NUC was straightforward, as the `ssh-keygen` command also works on Windows, as seen here:

![NUC keygen](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/SSHKeyGen.png)

Unfortunately, I found the `ssh-copy-id` command to be lacking on the host OS. As a result, I had to use an alternative method to share my public key with the jump box. After a rather excessive Google rabbithole and several failed attempts at creating a script to replace `ssh-copy-id`, I landed on the solution of first creating a key pair on the jump box to establish the correct folders, then using `cat` to copy the public key directly from my NUC to the jump box. The screenshot below shows both the key share and successful password-less logon.

![Share and Logon](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/ssh%20key%20share.png)

## Brute Force Access to Jump Box

Changing the password was straightforward as seen in the screenshot below. I used `passwd` to change the current password to one that I found in the .txt file of passwords.

![Password Change](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/PWChange.png)

I struggled for quite some time on this next section. I am not highly skilled with compiling source code from GitHub and occassionally wasn't sure if I was even using code that was made for Windows. I tried Hydra at first but wasn't able to get it installed properly. Next I tried Secure Shell Bruteforcer, but wasn't able to figure out how to use Go to compile the code. After that I looked into the nmap scripts suggested in the lab document but for some reason the nmap installer did not actually install nmap (it would run, but then nothing would change on the NUC and I didn't have access to nmap). Finally I saw the PuTTy installer on the Desktop and decided to utilize a script I had come across that used PuTTy as a base for brute forcing SSH access. As seen in the screenshot below, I was able to use the script combined with the password list provided in the lab document to brute force access to the jump box.

![SSH Brute Force](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%205/SuccessfulBruteForce.png)

An interesting feature I discovered when trying the brute force tool again was that PuTTyBrute keeps a log of attempts and if you try to brute force the same user and host again it will tell you it has already cracked it. I cleared the log and was able to run it again.
