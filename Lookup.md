#TryHackMe

# Nmap:
```c
┌──(kali㉿kali)-[~/Downloads]
└─$ rustscan -a 10.10.141.245      
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
Open 10.10.141.245:22
Open 10.10.141.245:80
[~] Starting Script(s)
[>] Script to be run Some("nmap -vvv -p {{port}} {{ip}}")

[~] Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-12-28 10:54 EST
Initiating Ping Scan at 10:54
Scanning 10.10.141.245 [4 ports]
Completed Ping Scan at 10:54, 0.19s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 10:54
Completed Parallel DNS resolution of 1 host. at 10:54, 0.01s elapsed
DNS resolution of 1 IPs took 0.01s. Mode: Async [#: 1, OK: 0, NX: 1, DR: 0, SF: 0, TR: 1, CN: 0]
Initiating SYN Stealth Scan at 10:54
Scanning 10.10.141.245 [2 ports]
Discovered open port 22/tcp on 10.10.141.245
Discovered open port 80/tcp on 10.10.141.245
Completed SYN Stealth Scan at 10:54, 0.18s elapsed (2 total ports)
Nmap scan report for 10.10.141.245
Host is up, received reset ttl 60 (0.15s latency).
Scanned at 2024-12-28 10:54:31 EST for 0s

PORT   STATE SERVICE REASON
22/tcp open  ssh     syn-ack ttl 60
80/tcp open  http    syn-ack ttl 60

Read data files from: /usr/share/nmap
Nmap done: 1 IP address (1 host up) scanned in 0.49 seconds
           Raw packets sent: 6 (240B) | Rcvd: 3 (128B)

                                   
```


```c
└─$ feroxbuster -u http://lookup.thm/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt 
                                                                                                                                                                                             
 ___  ___  __   __     __      __         __   ___
|__  |__  |__) |__) | /  `    /  \ \_/ | |  \ |__
|    |___ |  \ |  \ | \__,    \__/ / \ | |__/ |___
by Ben "epi" Risher 🤓                 ver: 2.11.0
───────────────────────────┬──────────────────────
 🎯  Target Url            │ http://lookup.thm/
 🚀  Threads               │ 50
 📖  Wordlist              │ /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt
 👌  Status Codes          │ All Status Codes!
 💥  Timeout (secs)        │ 7
 🦡  User-Agent            │ feroxbuster/2.11.0
 🔎  Extract Links         │ true
 🏁  HTTP methods          │ [GET]
 🔃  Recursion Depth       │ 4
───────────────────────────┴──────────────────────
 🏁  Press [ENTER] to use the Scan Management Menu™
──────────────────────────────────────────────────
403      GET        9l       28w      275c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
404      GET        9l       31w      272c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
200      GET        1l        0w        1c http://lookup.thm/login.php
200      GET       50l       84w      687c http://lookup.thm/styles.css
200      GET       26l       50w      719c http://lookup.thm/
[####################] - 5m     87652/87652   0s      found:3       errors:1      
[####################] - 5m     87650/87650   308/s   http://lookup.thm/           
```

