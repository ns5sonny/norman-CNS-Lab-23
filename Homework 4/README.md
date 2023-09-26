## Homework 4
1/c Charles Norman

Computer and Network Security

25SEP23

## Creating AD User
We had already created personal users in addition to the `cadetadm` user during the lab, so we just removed our users from the Administrators group for this step.
The screenshots below show both the basic account information and Member Of tabs for the user.

![Basic Account](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%204/Basic%20Account.png)

![Basic Member Of](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%204/Basic%20Member%20Of.png)

## Logon With Basic User
The following screenshot shows my login information from logging into the NUC with the user I had created in the active directory. 

![NUC Login](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%204/NUC%20User%20Account.png)

## Changing PowerShell Permissions
We decided to set LocalMachine and CurrentUser execution policies to AllSigned since that is the option that allows us to run scripts we write on the machine while still maintaining some amount of security. The Process scope only applies to the current PowerShell session so this remains unchanged. MachinePolicy and UserPolicy scopes must be changed via Group Policy rather than PowerShell so both remain unchanged (the initial value is Undefined, which means the effective execution policy is Restricted).
The output of the `Get-ExecutionPolicy -list` command is seen below:

![Execution Policies](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%204/ExecutionPolicy.png)

## Unique PowerShell Script
For my unique script, I wrote a one-liner that creates a .txt file on the desktop, similar to the Linux `touch` command. The successful execution of the script is seen below (along with the script in Notepad):

![Script Output](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%204/ScriptOutput.png)

## BadBlood Script
Initially running the BadBlood script resulted in constant errors since the script was not allowed to create new users. However, the output was mildly entertaining:

![BadBlood muck](https://github.com/ns5sonny/norman-CNS-Lab-23/blob/main/Homework%204/badblood%20muck.png)
