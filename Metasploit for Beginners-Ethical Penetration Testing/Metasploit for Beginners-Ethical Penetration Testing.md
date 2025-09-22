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

![alt text](rapid7 image)

* By clicking on the first site, we can find out that this version number was disclosed in 2011, which means that it is an old vulnerability
* We can also find instructions on how to use and exploit this Metasploi module

![alt text](metasploit module image)

## Task 3: Introduction to Metasploit











