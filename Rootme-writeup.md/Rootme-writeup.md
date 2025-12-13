
**title:**  "[RootMe] - TryHackMe"

**date:**  10-12-2025

**Difficulty:** Easy

**Time to complete:** ~3 hours

**url:**  https://tryhackme.com/room/rrootme

## categories:

- Nmap scan

- Gobuster

- reverse shell moneky

- SUID Exploitation

## ScreenShots:

1.https://github.com/ahmadqattan2001-art/tryhackme-writeups/blob/main/screenshots/WhatsApp%20Image%202025-12-11%20at%2016.12.35_92dfc5c1.jpg

2. https://github.com/ahmadqattan2001-art/tryhackme-writeups/blob/main/screenshots/WhatsApp%20Image%202025-12-11%20at%2016.12.34_32645003.jpg

3.https://github.com/ahmadqattan2001-art/tryhackme-writeups/blob/main/screenshots/WhatsApp%20Image%202025-12-11%20at%2016.12.35_52424e25.jpg

4. https://github.com/ahmadqattan2001-art/tryhackme-writeups/blob/main/screenshots/Screenshot%202025-12-11%20161150.png
## Skills gained: 
SUID exploitation, gobuster, upload various php versions, listening to ports by Netcat.

## Goal

To exploit the target system, escalate to root privileges, and access sensitive information such as credentials, configuration files, and other critical data.

## Tools Used

- Nmap

- Gobuster

-  Netcat

- php reverse monkey

## Attack Chain (Red Team)

Mentioned in the 4th photo that i uploaded  in the "screenshots" section

## Root Cause

File Upload Bypass

Initial attempts to upload a PHP reverse shell were unsuccessful:

-  **`.php`** - Blocked by the application

-  **`.php2`** - Upload successful, but failed to execute

-  **`.php3`** - Upload successful, but failed to execute

After testing multiple extensions, **`.phtml`** was successfully uploaded and executed, allowing me to establish a reverse shell connection.

## Mitigation

1. Remove SUID bit from `/usr/bin/python`

2. Monitor unusual file uploads
