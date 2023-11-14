## Homework 8
1/c Charles Norman

Computer and Network Security

16NOV23

## Medusa
The tool I chose to research and utilize during the coming lab is Medusa. Medusa is a login brute-forcer that advertises itself as being "speedy, parallel, and modular" while supporting as many services that allow remote authentication as possible. The tool is designed for a Unix-based OS (making it available for MacOS as well as Linux) and written in C. The source code can be found on GitHub at the following link: [Medusa GitHub Code](https://github.com/jmk-foofus/medusa). Medusa is thread-based, which separates it from the process-based brute forcing tool Hydra. The author’s forum (linked [here]( http://foofus.net/?page_id=51)) mentions that this thread structuring also allows the tool to attack multiple hosts at once, which I found interesting since I didn’t expect to consider a situation that would require concurrent attacks on multiple hosts simultaneously. It supports wordlists for both the username and password, although these can also be provided by the user in the commandline, as well as a flag specifying the target service (VNC, POP3, HTTP, FTP, SSH, MS-SQL, etc). This tool doesn’t exactly attack a specific CWE or CVE, since it tries to find a username and password combination that has already been discovered or suggested by a combination of wordlists. Still, it’s flexibility and speed make it an interesting tool to use for this homework. Below is a screenshot of Medusa running on my system: 

![Medusa Help Screen]()

## Medusa Demonstration
As mentioned above, Medusa is a flexible and easy-to-use tool, meaning I can essentially point and shoot with the built-in Kali wordlists, as shown below:

![Medusa In Action]()
