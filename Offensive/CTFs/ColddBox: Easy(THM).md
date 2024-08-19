Hints and notes:

    wpscan
    wp-config.php
    Scratch the surface, no rabbit hole

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

I began with an Nmap scan, as usual. I always perform a full scan (-p-), but I start by running a quick scan before the full scan completes.

![nmap](https://github.com/user-attachments/assets/6e76272b-f1eb-485f-827e-e7fc9a1a12b2)

From the scan results, I saw that only 2 (80,4512) port was open, so I proceeded to check the website. Initially, there didn’t seem to be anything interesting on the surface.

Next, I used Gobuster for directory enumeration. As shown in the picture, I found an intriguing directory: /hidden.

![gobuster](https://github.com/user-attachments/assets/2b4b7b70-1864-420d-b52f-9aeeb2109d3b)

Following that, I tried wpscan, which is a tool designed for scanning WordPress sites. However, the initial scan (wpscan --url $IP) didn’t reveal anything particularly impressive.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

After my initial enumeration, I analyzed the results:

1) I searched for the version of WordPress (which was revealed in the Nmap scan). After some research, I found a number of vulnerabilities. You can check them out here:  https://www.cybersecurity-help.cz/vdb/wordpress_org/wordpress/4.1.31/

2) Checking the /hidden directory revealed three usernames.

![hidden directory](https://github.com/user-attachments/assets/3fd187fb-5094-40ef-bf9f-513ea5b2451f)

With the usernames in hand, I improved my wpscan by brute-forcing login credentials. Eventually, I found the password c0ldd, which allowed me to log in to the site.

![wpscan-syntax](https://github.com/user-attachments/assets/f46e65e2-137a-41e5-bd34-bde5e64dd74d)

![wpscan - user brute force](https://github.com/user-attachments/assets/3c0475e0-d7df-4216-b145-2c39aecae523)

And I got the c0ldd password - which logged in site.

Result of research led me to an Arbitrary File Upload vulnerability. WordPress versions before 5.8 lack support for the Update URI plugin header, making it easier for attackers to execute arbitrary code via a supply-chain attack, particularly against WordPress installations that use plugins with names satisfying certain constraints but are not yet in the WordPress Plugin Directory. You can read more about this here: https://wpscan.com/vulnerability/95e01006-84e4-4e95-b5d7-68ea7b5aa1a8/

**This vulnerability essentially handed the attacker an easy win. The administrator should have updated the website.**

Since the site was PHP-based, I used a PHP reverse shell to gain a foothold on the box. After configuring the IP and port correctly in the script, all that was left was to set up a listener.

![file-uploaded](https://github.com/user-attachments/assets/3fdb84ae-3e18-40a8-82a2-7776543d8a64)


I successfully gained shell access but did not have permission to read the user.txt file at this point, which is where I got stuck. 

![foothold](https://github.com/user-attachments/assets/fdf417be-cb0d-492b-9359-0e32605ca680)

![foothold-upgarde](https://github.com/user-attachments/assets/b560dd08-5b3f-4e6b-ab21-987021660550)


`The wp-config.php file is a configuration file created during the WordPress installation process. It stores database information such as the database name, username, password, and host. In addition to establishing a connection between your WordPress site and its database, WordPress also uses the wp-config.`

Above info says it enough; checking the /var/www/html/wp-config.php gave me c0ldd password, even though it is for the DB, it is worth to try to login as a c0ldd in a shell; and that was correct assumption.

![coldd-pasword](https://github.com/user-attachments/assets/c4b9eda8-eb71-42ad-8182-65ca9cf23d6a)

![entering as a coldd](https://github.com/user-attachments/assets/ab59e55a-0acf-4968-b605-516bd5276cde)

With that we got the user.txt file:

![cat-user txt](https://github.com/user-attachments/assets/2751ddee-d0e4-4104-9ab6-f78cb4f3a403)

After becoming the low-privileged user, I initiated my usual privilege escalation process by running sudo -l. The results revealed some interesting findings.

From there - we go -> https://gtfobins.github.io/gtfobins/vim/; since we can run vim as a root. Trying `sudo vim -c ':!/bin/sh` gives us a root access and root.txt

![root txt](https://github.com/user-attachments/assets/afea3fee-3e15-4479-9b1d-0095c8c1958b)
