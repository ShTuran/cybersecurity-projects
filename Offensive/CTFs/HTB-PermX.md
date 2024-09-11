Result of `nmap` scan:

`Host discovery disabled (-Pn). All addresses will be marked 'up' and scan times may be slower.
Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-09-11 07:11 EDT
NSE: Loaded 156 scripts for scanning.
NSE: Script Pre-scanning.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.00s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.00s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.00s elapsed
Initiating Connect Scan at 07:11
Scanning permx.htb (10.10.11.23) [65535 ports]
Discovered open port 22/tcp on 10.10.11.23
Discovered open port 80/tcp on 10.10.11.23
Increasing send delay for 10.10.11.23 from 0 to 5 due to 11 out of 31 dropped probes since last increase.
Completed Connect Scan at 07:11, 13.96s elapsed (65535 total ports)
Initiating Service scan at 07:11
Scanning 2 services on permx.htb (10.10.11.23)
Completed Service scan at 07:11, 6.19s elapsed (2 services on 1 host)
NSE: Script scanning 10.10.11.23.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 2.69s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.38s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.00s elapsed
Nmap scan report for permx.htb (10.10.11.23)
Host is up, received user-set (0.10s latency).
Scanned at 2024-09-11 07:11:04 EDT for 23s
Not shown: 65515 filtered tcp ports (no-response)
PORT     STATE  SERVICE          REASON       VERSION
21/tcp   closed ftp              conn-refused
22/tcp   open   ssh              syn-ack      OpenSSH 8.9p1 Ubuntu 3ubuntu0.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 e2:5c:5d:8c:47:3e:d8:72:f7:b4:80:03:49:86:6d:ef (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBAyYzjPGuVga97Y5vl5BajgMpjiGqUWp23U2DO9Kij5AhK3lyZFq/rroiDu7zYpMTCkFAk0fICBScfnuLHi6NOI=
|   256 1f:41:02:8e:6b:17:18:9c:a0:ac:54:23:e9:71:30:17 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIP8A41tX6hHpQeDLNhKf2QuBM7kqwhIBXGZ4jiOsbYCI
25/tcp   closed smtp             conn-refused
80/tcp   open   http             syn-ack      Apache httpd 2.4.52
|_http-server-header: Apache/2.4.52 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: eLEARNING
111/tcp  closed rpcbind          conn-refused
113/tcp  closed ident            conn-refused
135/tcp  closed msrpc            conn-refused
139/tcp  closed netbios-ssn      conn-refused
256/tcp  closed fw1-secureremote conn-refused
443/tcp  closed https            conn-refused
445/tcp  closed microsoft-ds     conn-refused
554/tcp  closed rtsp             conn-refused
587/tcp  closed submission       conn-refused
993/tcp  closed imaps            conn-refused
1025/tcp closed NFS-or-IIS       conn-refused
1723/tcp closed pptp             conn-refused
3306/tcp closed mysql            conn-refused
3389/tcp closed ms-wbt-server    conn-refused
8080/tcp closed http-proxy       conn-refused
8888/tcp closed sun-answerbook   conn-refused
Service Info: Host: 127.0.0.1; OS: Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.00s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.00s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 07:11
Completed NSE at 07:11, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 23.43 seconds`
