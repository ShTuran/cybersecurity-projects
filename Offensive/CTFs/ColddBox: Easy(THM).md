Hints and notes:

    wpscan
    wp-config.php
    Scratch the surface, no rabbit hole

As always I begin with nmap scan (I always scan fully -p- and before it completes I run short scan)

We that only one port is open, let's check the site

Nothing intereting to see there.

After that, I have used gobuster and as seen from picture I have found one directory which is interesting /hidden

Lastly, I have tried the wpscan which is designed for Wordpress sites; nothing impressive with wpscan --url $IP

After doing initial enumeration, I look through the results:

    I searched the version of Wordpress (which we got it from nmap scan) and found many vulnerabilities -> check out the link: https://www.cybersecurity-help.cz/vdb/wordpress_org/wordpress/4.1.31/

And then checked the /hidden directory; from this, we get see three usernames.

Since we got the usernames, I have improved my wpscan by brute forcing.

And I got the c0ldd password - which logged in site.

From the simple research, we see that there is a Arbitrary file upload vulnerability.

WordPress before 5.8 lacks support for the Update URI plugin header. This makes it easier for remote attackers to execute arbitrary code via a supply-chain attack against WordPress installations that use any plugin for which the slug satisfies the naming constraints of the WordPress.org Plugin Directory but is not yet present in that directory. Source: https://wpscan.com/vulnerability/95e01006-84e4-4e95-b5d7-68ea7b5aa1a8/

This is win for attacker. And admin should have update the website.

Since site is .php based php-reverse shell will help us to get a foothold on a box. After configuring the $IP and port accordingly in the script, al we need is a listener.

And we got the shell. But I have not had any permission to cat the user.txt file. (which is where i got stucked)

The wp-config. php file is a configuration file created during the WordPress installation process. It stores database information such as the database name, username, password, and host. In addition to establishing a connection between your WordPress site and its database, WordPress also uses the wp-config.

Above info says it enough; checking the /var/www/html/wp-config.php gave me c0ldd password, even though it is for the DB, it is worth to try to login as a c0ldd in a shell; and that was correct assumption.

With that we got the user.txt file:

After being the low-level user, I always start PE with sudo -l and we see a some interesting findings.

From there - we go -> https://gtfobins.github.io/gtfobins/vim/; since we can run vim as a root. Trying sudo vim -c ':!/bin/sh' gives us a root access and root.txt
