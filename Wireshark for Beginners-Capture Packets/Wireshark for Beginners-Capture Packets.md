# Wireshark for Beginners: Capture Packets


In this lab I will learn how to set up and use Wireshark to capture, save, and filter HTTP and HTTPS packets.

## Task 1: Install and Set Up Wireshark on Ubuntu

* To install the most recent stable release of Wireshark on Ubuntu Linux, employ the add-apt-repository command: `sudo add-apt-repository ppa:wireshark-dev/stable`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/e78e64250774eaa4c0cdda2837da808762b2c46f/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Recent%20Stable%20Release.webp)

* Wireshark should not be run as a superuser for security reasons.
* The user can be added to the Wireshark group to add packet capture capabilities: `sudo usermod -aG wireshark $USER`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/26501b3ec805e2ecdeef6ea28210b347a898b4c5/Wireshark%20for%20Beginners-Capture%20Packets/Screenshots/Add%20User%20to%20Wireshark%20Group.webp)



