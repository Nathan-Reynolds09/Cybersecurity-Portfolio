# Wireshark for Beginners: Capture Packets


In this lab I will learn how to set up and use Wireshark to capture, save, and filter HTTP and HTTPS packets.

## Task 1: Install and Set Up Wireshark on Ubuntu

* To install the most recent stable release of Wireshark on Ubuntu Linux, employ the add-apt-repository command: `sudo add-apt-repository ppa:wireshark-dev/stable`


![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/e78e64250774eaa4c0cdda2837da808762b2c46f/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Recent%20Stable%20Release.webp)

* Wireshark should not be run as a superuser for security reasons.
* The user can be added to the Wireshark group to add packet capture capabilities: `sudo usermod -aG wireshark $USER`


![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/26501b3ec805e2ecdeef6ea28210b347a898b4c5/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Add%20User%20to%20Wireshark%20Group.webp)

## Task 2: Start a Packet Capture on an Ethernet Port and Save It to File
* Using Wireshark, the wired interface includes the ethernet packet capture


![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/bf9d5ca505d0615148d1ecf04b9840fca587315a/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Wired%20Interface.png)

* Start the packet capture by clicking the blue fin in the top left corner
* To stop the packet capture click the red stop icon


![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/bf9d5ca505d0615148d1ecf04b9840fca587315a/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Stop%20Packet%20Capture.png)

* Wireshark allows users to save the packet capture
* Saving a capture is only possible when the capture has stopped


![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/bf9d5ca505d0615148d1ecf04b9840fca587315a/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Save%20Capture.png)

## Task 3: Use a Display Filter to Detect HTTPS Packets

* Using what was learned in Task 3, start a packet capture and go to duckduckgo.com while the packet capture is running. When the site it loaded, stop the packet capture and save it to a file
* To diplay only HTTPS traffic, use a filter on port 443: `tcp.port == 443`
* After applying the display filter, look for the TLSv protocol that says `Client Hello`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/a6543c90056d84564da0e3674f69306741a35a10/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Display%20Filter.png)

* Take the destination IP you see for the TLSv protocol and enter it into the browser

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/a6543c90056d84564da0e3674f69306741a35a10/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Enter%20IP%20Address.png)

* When the destination IP is entered, duckduckgo.com is the site associated with the IP






