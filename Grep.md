---
date: 2024-12-28T16:53:00
tags:
  - TryHackMe
Hardlevel: easy
---
# GREP:

## NMAP SCAN:
```c
──(kali㉿kali)-[~]
└─$ rustscan -a 10.10.101.204    
.----. .-. .-. .----..---.  .----. .---.   .--.  .-. .-.
| {}  }| { } |{ {__ {_   _}{ {__  /  ___} / {} \ |  `| |
| .-. \| {_} |.-._} } | |  .-._} }\     }/  /\  \| |\  |
`-' `-'`-----'`----'  `-'  `----'  `---' `-'  `-'`-' `-'
The Modern Day Port Scanner.
________________________________________
: https://discord.gg/GFrQsGy           :
: https://github.com/RustScan/RustScan :
 --------------------------------------
Real hackers hack time ⌛

[~] The config file is expected to be at "/home/kali/.rustscan.toml"
[!] File limit is lower than default batch size. Consider upping with --ulimit. May cause harm to sensitive servers
[!] Your file limit is very small, which negatively impacts RustScan's speed. Use the Docker image, or up the Ulimit with '--ulimit 5000'. 
Open 10.10.101.204:22
Open 10.10.101.204:80
Open 10.10.101.204:443
Open 10.10.101.204:51337
[~] Starting Script(s)
[>] Script to be run Some("nmap -vvv -p {{port}} {{ip}}")

[~] Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-12-28 06:28 EST
Initiating Ping Scan at 06:28
Scanning 10.10.101.204 [4 ports]
Completed Ping Scan at 06:28, 0.19s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 06:28
Completed Parallel DNS resolution of 1 host. at 06:28, 0.02s elapsed
DNS resolution of 1 IPs took 0.02s. Mode: Async [#: 1, OK: 0, NX: 1, DR: 0, SF: 0, TR: 1, CN: 0]
Initiating SYN Stealth Scan at 06:28
Scanning 10.10.101.204 [4 ports]
Discovered open port 51337/tcp on 10.10.101.204
Discovered open port 443/tcp on 10.10.101.204
Discovered open port 80/tcp on 10.10.101.204
Discovered open port 22/tcp on 10.10.101.204
Completed SYN Stealth Scan at 06:28, 0.18s elapsed (4 total ports)
Nmap scan report for 10.10.101.204
Host is up, received echo-reply ttl 60 (0.15s latency).
Scanned at 2024-12-28 06:28:40 EST for 1s

PORT      STATE SERVICE REASON
22/tcp    open  ssh     syn-ack ttl 60
80/tcp    open  http    syn-ack ttl 60
443/tcp   open  https   syn-ack ttl 60
51337/tcp open  unknown syn-ack ttl 60

Read data files from: /usr/share/nmap
Nmap done: 1 IP address (1 host up) scanned in 0.51 seconds
           Raw packets sent: 8 (328B) | Rcvd: 5 (204B)

```

```c

```