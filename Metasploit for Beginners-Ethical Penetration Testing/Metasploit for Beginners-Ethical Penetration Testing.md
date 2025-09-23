# Metasploit for Beginners: Ethical Penetration Testing
In this project I will learn the key tools and techniques needed to conduct ethical hacking and penetration testing. The goals of this project are:
* Utilize an exploit using Metasploit to gain access to a vulnerable system
* Perform a Vulnerability Scan Analysis to enable effective vulnerability reporting
* Author comprehensive penetration testing reports with results that will enable a company to fix their vulnerabilities

There are some pre-requisite steps to take in order to complete this project
1. Download VMWare [Download for Windows and Linux](https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion)
2. Upload Kali Linuz Virtual Machine to VMWare [Download for Kali Linux Virtual Machine](https://www.kali.org/get-kali/#kali-virtual-machines)
3. Upload the Metaploitable2 Machine to VMWare [Download for Metasploit2](https://sourceforge.net/projects/metasploitable/) [Walkthrough for Metaploitable2](https://www.youtube.com/watch?v=LnRgCop4jkk)
4. Connect the Boxes in VMWare so They Can Ping Each Other [Guide](https://www.ubackup.com/enterprise-backup/how-to-connect-one-virtual-machine-to-another.html)

## Task 1: Use Nmap to Scan for Vulerable Services
* Make sure you have both the attacker machine (Kali Linux) and the target machine (Metasploitable) up and running through VMWare
* Type `ip a` into the target machine to find the ip address: `192.168.57.129`
* On the attacker machine input `ping 192.168.57.129` to make sure that the machines are connected

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/a0294060f801e3b3fb96deeb17ddab1e41bfd65d/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/ping.PNG)

* Type `nmap -h` into the terminal on Kali Linux to view the manual for nmap.

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/b77c9c4c469402b02334e3543d8cd45cd239f221/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/nmap%20h.PNG)

* To perform a nmap scan type `nmap 192.168.57.129`
* Take note on how many ports there are and how many are open. The more open ports there are, the bigger attack surface

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/a0294060f801e3b3fb96deeb17ddab1e41bfd65d/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/nmap%20scan.PNG)

* To perform a more in-depth scan use `nmap -sC 192.168.57.129`
* This will give way more information than just if a port is open or closed

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/a0294060f801e3b3fb96deeb17ddab1e41bfd65d/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/nmap%20sC.PNG)

* Add `-sV` into the scan by inputing `nmap -sC -sV 192.168.57.129`
* `-sV` stands for version number
* For example, from the scan we found out that the ftp service has a version number of `vsftpd 2.3.4`
* This is important because by knowing this version number we can look up whether it is outdated, exploitable, and work from there to try to break the machine

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/a0294060f801e3b3fb96deeb17ddab1e41bfd65d/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/nmap%20sV.PNG)

## Task 2: Vulnerability Research with Google Dorking
* We are going to find resources that give us information about the version number we found from before
* Open Firefox and type in `vsftpd 2.3.4 vulnerability site:rapid7.com`
* `site:rapid7.com` makes it so all the search results are from Rapid7

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/b5d6bae9527b78149a3a086ce6a8ba010b244b22/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/rapid7.PNG)

* By clicking on the first site, we can find out that this version number was disclosed in 2011, which means that it is an old vulnerability
* We can also find instructions on how to use and exploit this Metasploit module

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/b5d6bae9527b78149a3a086ce6a8ba010b244b22/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/metasploit%20module.PNG)

## Task 3: Introduction to Metasploit
* To start up Metasploit input `msfconsole`
* One piece of information we get is all the modules listed

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/7cab135143499e72300ead8dedf6dd93bfd12efb/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/modules.PNG)

* Input`help` into the terminal to see commands in Metasploit
* Some commands will look familiar because some of the commands are also Linux commands
* You will see some commands that only exist within Metasploit itself
* In order to get out of the Metasploit terminal, simply type `exit`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/7cab135143499e72300ead8dedf6dd93bfd12efb/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/help.PNG)

## Task 4: Load Your First Metasploit Module
* Get back into the Metasploit console by typing `msfconsole`
* Input `search vsftpd 2.3.4` into the Metasploit console
* We will see there is only one module for this particular version

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/1ffb9dadd5295e3f6dbc54bb8539c2d1e725e9f2/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/search%20vsftps%202.3.4.PNG)

* In order to load this module input `use 0`
* There will be a change in the command line
* Input `show options` into the terminal to view the list of things we need to configure in order to properly execute our attack

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/1ffb9dadd5295e3f6dbc54bb8539c2d1e725e9f2/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/show%20options.PNG)

## Task 5: Configure Your First Metasploit Module
* In order to run our attack, we have to configure `RHOSTS` to be the correct IP address and then exploit it
* To do this type `set rhosts 192.168.57.129`
* To make sure that we have configured `RHOSTS` input `show options` again in the terminal and we should see the IP address next to `RHOSTS`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/f05aaebd73a0c89a06eadd72b21c73c7b24c068d/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/rhosts.PNG)

* Now that the attack is pointed to the right machine all we need to do is type `exploit` for the attack to run

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/f05aaebd73a0c89a06eadd72b21c73c7b24c068d/Metasploit%20for%20Beginners-Ethical%20Penetration%20Testing/Images/exploit.PNG)

## Task 6: Establishing Persistence
* We have to create a backdoor account to allow us to log back into the system more easily in the future
* In order to do this type `adduser backdoor`
* It will prompt you to create a password and enter some information about the user. We don't have to fill out the information, so I kept all of it blank

![alt text](backdoor user image)

* Now we can login to the account we just created. We can do that by opening another tab and typing `ssh -oHostKeyAlgorithms=+ssh-rsa backdoor@192.168.57.129` and it will ask for the password you previously created, which in this case is 'pass'

![alt text](login image)

## Task 7: Report Our Findings
* We are going to fill out a Penetration Testing Report showcasing all of our findings to an organization called AeroTech who we tested for vulnerabilities



