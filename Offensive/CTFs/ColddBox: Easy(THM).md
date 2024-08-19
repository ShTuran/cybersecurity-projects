Hints and Notes:

    wpscan
    wp-config.php
    Scratch the surface, no rabbit hole

I began with an Nmap scan, as usual. I always perform a full scan (-p-), but I start by running a quick scan before the full scan completes.

From the scan results, I saw that only one port was open, so I proceeded to check the website. Initially, there didn’t seem to be anything interesting on the surface.

Next, I used Gobuster for directory enumeration. As shown in the picture, I found an intriguing directory: /hidden.

Following that, I tried wpscan, which is a tool designed for scanning WordPress sites. However, the initial scan (wpscan --url $IP) didn’t reveal anything particularly impressive.

After my initial enumeration, I analyzed the results:

    I searched for the version of WordPress (which was revealed in the Nmap scan). After some research, I found a number of vulnerabilities. You can check them out here: WordPress Vulnerabilities.

    Checking the /hidden directory revealed three usernames.

With the usernames in hand, I improved my wpscan by brute-forcing login credentials. Eventually, I found the password c0ldd, which allowed me to log in to the site.

A bit of research led me to an Arbitrary File Upload vulnerability. WordPress versions before 5.8 lack support for the Update URI plugin header, making it easier for attackers to execute arbitrary code via a supply-chain attack, particularly against WordPress installations that use plugins with names satisfying certain constraints but are not yet in the WordPress Plugin Directory. You can read more about this here: WordPress Arbitrary File Upload Vulnerability.

This vulnerability essentially handed the attacker an easy win. The administrator should have updated the website.

Since the site was PHP-based, I used a PHP reverse shell to gain a foothold on the box. After configuring the IP and port correctly in the script, all that was left was to set up a listener.

I successfully gained shell access but did not have permission to read the user.txt file at this point, which is where I got stuck.

At this stage, I turned my attention to the wp-config.php file. This file, created during the WordPress installation process, stores database information such as the database name, username, password, and host. It also establishes the connection between WordPress and its database.

Given this information, I checked /var/www/html/wp-config.php and found the same c0ldd password. Although this password was for the database, I decided to try it for shell access as well, and fortunately, my assumption was correct. This granted me access to the user.txt file.

After becoming the low-privileged user, I initiated my usual privilege escalation process by running sudo -l. The results revealed some interesting findings.

From here, I followed the instructions on GTFOBins, which indicated that I could run vim as root. Using sudo vim -c ':!/bin/sh' successfully gave me root access, allowing me to retrieve the root.txt file.
