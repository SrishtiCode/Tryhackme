# GamingServer

An Easy Boot2Root box for beginners

Connect with server and start.

We start with RECON

1. Port Scanning
```
rustscan -a 10.10.174.135 -r 1-65535 --ulimit 5000 -- -sV -T4 -oN rustscan_nmap.txt
```
Result
```
[~] The config file is expected to be at "/home/srishti/.rustscan.toml"
[~] Automatically increasing ulimit value to 5000.
Open 10.10.174.135:22
Open 10.10.174.135:80
[~] Starting Script(s)
[>] Running script "nmap -vvv -p {{port}} -{{ipversion}} {{ip}} -sV -T4 -oN rustscan_nmap.txt" on ip 10.10.174.135
Depending on the complexity of the script, results may take some time to appear.
[~] Starting Nmap 7.95 ( https://nmap.org ) at 2025-07-03 20:21 IST
NSE: Loaded 47 scripts for scanning.
Initiating Ping Scan at 20:21
Scanning 10.10.174.135 [4 ports]
Completed Ping Scan at 20:21, 0.21s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 20:21
Completed Parallel DNS resolution of 1 host. at 20:21, 0.00s elapsed
DNS resolution of 1 IPs took 0.01s. Mode: Async [#: 1, OK: 0, NX: 1, DR: 0, SF: 0, TR: 1, CN: 0]
Initiating SYN Stealth Scan at 20:21
Scanning 10.10.174.135 [2 ports]
Discovered open port 22/tcp on 10.10.174.135
Discovered open port 80/tcp on 10.10.174.135
Completed SYN Stealth Scan at 20:21, 0.24s elapsed (2 total ports)
Initiating Service scan at 20:21
Scanning 2 services on 10.10.174.135
Completed Service scan at 20:21, 6.49s elapsed (2 services on 1 host)
NSE: Script scanning 10.10.174.135.
NSE: Starting runlevel 1 (of 2) scan.
Initiating NSE at 20:21
Completed NSE at 20:21, 0.86s elapsed
NSE: Starting runlevel 2 (of 2) scan.
Initiating NSE at 20:21
Completed NSE at 20:21, 0.83s elapsed
Nmap scan report for 10.10.174.135
Host is up, received timestamp-reply ttl 60 (0.19s latency).
Scanned at 2025-07-03 20:21:12 IST for 8s

PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 60 OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    syn-ack ttl 60 Apache httpd 2.4.29 ((Ubuntu))
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Read data files from: /usr/share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 8.92 seconds
           Raw packets sent: 6 (240B) | Rcvd: 3 (128B)

```
So two ports are open port 22 and port 80

2. Website recon
We go to the website at port 80 and it shows us a webpage.

Will hit the Ctrl+U to view the source page.

So, in comment we saw a comment which talking to John. So, maybe it is a username.

We also have many options to go.
When we click on the Draagon lore and we get the upload option.
When we click it, it takes us to the upload directory which have following directories.

 We have a directory which include the password, so we save it on the pc.
 ```
 wget "http://10.10.174.135/uploads/dict.lst"
```

3. Directory Search
```
 gobuster dir -u http://10.10.174.135/ -w /usr/share/wordlists/rockyou.txt
```
We found the directory \secret

We have a secret key


