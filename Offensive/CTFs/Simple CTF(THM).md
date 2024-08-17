***Question-based***

# How many services are running under port 1000?

2 

21 and 80

![nmap](https://github.com/user-attachments/assets/916a2955-ec10-4002-8623-6d338ebb727b)

# What is running on the higher port?

As shown from above picture

2222/tcp open   ssh     syn-ack

# What's the CVE you're using against the application? 

![gobuster](https://github.com/user-attachments/assets/975b31f6-c77e-4732-b8f5-1776ee24d267)

- gobuster - find the dir -> /simple 

- searchsploit -> searched the version of CMS

`CVE-2019-9053`

![robots txt](https://github.com/user-attachments/assets/c244e4b4-e4a3-40ca-a9ef-f7d543608a08)

nothing to do with robots.txt

# To what kind of vulnerability is the application vulnerable?

sqli

# What's the password?

for that I run `python2 -m pip install termcolor' beacuse it was missing module to run exploit in my case

after that `python2 exploit.py -u http://$IP/simple` will give the result

![resultof exploit](https://github.com/user-attachments/assets/6753c614-ca0f-4ebc-a8bc-6ba4ecd590d7)

After running the the exploit -> getting password:salt -> cracking with hashcat -> gives us password

![hashcat-result](https://github.com/user-attachments/assets/59af39a1-35e5-432c-92ba-c9b8f654b569)


# Where can you login with the details obtained?

The next port was ssh -> so ssh was logical, since ftp did not give us anything even though it has anonymous access

![ftp](https://github.com/user-attachments/assets/7e174b3f-0fe3-46ab-96a0-0a41b9c44fb5)

# What's the user flag?

It is located under /home directory

![user txt](https://github.com/user-attachments/assets/69fc404c-08e3-4c22-af15-a0b19b7a000f)

# Is there any other user in the home directory? What's its name?

![other-user](https://github.com/user-attachments/assets/44f990d7-28c2-41a7-ab3a-da6aef2240ea)

Going to /home directory and listing that directory will give us answer.

# What can you leverage to spawn a privileged shell?

![sudo -l](https://github.com/user-attachments/assets/79b4e340-01ac-4fe8-ae8a-ca9a2117e44e)

`sudo -l` gives us answer 

# What's the root flag?

And https://gtfobins.github.io/gtfobins/vim/#sudo 

![root](https://github.com/user-attachments/assets/c7ab9dea-f6b1-45a5-852f-ade0e4dd6686)

using above command will give us root access.
