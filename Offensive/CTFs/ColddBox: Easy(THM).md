Hints and notes:

    wpscan
    wp-config.php
    Scratch the surface, no rabbit hole

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

I began with an Nmap scan, as usual. I always perform a full scan (-p-), but I start by running a quick scan before the full scan completes.

From the scan results, I saw that only one port was open, so I proceeded to check the website. Initially, there didn’t seem to be anything interesting on the surface.

Next, I used Gobuster for directory enumeration. As shown in the picture, I found an intriguing directory: /hidden.

Following that, I tried wpscan, which is a tool designed for scanning WordPress sites. However, the initial scan (wpscan --url $IP) didn’t reveal anything particularly impressive.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

After my initial enumeration, I analyzed the results:

1) I searched for the version of WordPress (which was revealed in the Nmap scan). After some research, I found a number of vulnerabilities. You can check them out here:  https://www.cybersecurity-help.cz/vdb/wordpress_org/wordpress/4.1.31/

2) Checking the /hidden directory revealed three usernames.


With the usernames in hand, I improved my wpscan by brute-forcing login credentials. Eventually, I found the password c0ldd, which allowed me to log in to the site.


And I got the c0ldd password - which logged in site.

A bit of research led me to an Arbitrary File Upload vulnerability. WordPress versions before 5.8 lack support for the Update URI plugin header, making it easier for attackers to execute arbitrary code via a supply-chain attack, particularly against WordPress installations that use plugins with names satisfying certain constraints but are not yet in the WordPress Plugin Directory. You can read more about this here: https://wpscan.com/vulnerability/95e01006-84e4-4e95-b5d7-68ea7b5aa1a8/

**This vulnerability essentially handed the attacker an easy win. The administrator should have updated the website.**

Since the site was PHP-based, I used a PHP reverse shell to gain a foothold on the box. After configuring the IP and port correctly in the script, all that was left was to set up a listener.

I successfully gained shell access but did not have permission to read the user.txt file at this point, which is where I got stuck. 


`The wp-config.php file is a configuration file created during the WordPress installation process. It stores database information such as the database name, username, password, and host. In addition to establishing a connection between your WordPress site and its database, WordPress also uses the wp-config.`


Above info says it enough; checking the /var/www/html/wp-config.php gave me c0ldd password, even though it is for the DB, it is worth to try to login as a c0ldd in a shell; and that was correct assumption.

With that we got the user.txt file:

After becoming the low-privileged user, I initiated my usual privilege escalation process by running sudo -l. The results revealed some interesting findings.

From there - we go -> https://gtfobins.github.io/gtfobins/vim/; since we can run vim as a root. Trying `sudo vim -c ':!/bin/sh` gives us a root access and root.txt
