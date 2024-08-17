***Question-based***

# How many services are running under port 1000?

2 21 and 80

# What is running on the higher port?

2222/tcp open   ssh     syn-ack

# What's the CVE you're using against the application? 

gobuster - find the dir -> simple -> 
searchsploit  -> searched the version of CMS

CVE-2019-9053

# To what kind of vulnerability is the application vulnerable?

sqli

# What's the password?

for that run `python2 -m pip install termcolor' beacuse it was missing module to run exploit 

after that `python2 exploit.py -u http://$IP/simple` will give the result

After running the the exploit -> getting password:salt -> cracking with hashcat -> gives us password


# Where can you login with the details obtained?

The next port was ssh -> so ssh was logical, since ftp did not give us anything even though it has anonymous access

# What's the user flag?

It is located under /home directory
 
# Is there any other user in the home directory? What's its name?

Going to /home directory and listing that directory will give us answer.

# What can you leverage to spawn a privileged shell?

`sudo -l` gives us answer 

# What's the root flag?

And https://gtfobins.github.io/gtfobins/vim/#sudo 

using above command will give us root access.
