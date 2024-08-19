As always I begin with nmap scan (I always scan fully `-p-` and before it completes I run short scan)


We that only one port is open, let's check the site


Nothing intereting to see there.


After that, I have used `gobuster` and as seen from picture I have found one directory which is interesting `/hidden`


Lastly, I have tried the `wpscan` which is designed for Wordpress sites; nothing impressive with `wpscan --url $IP`

------------------------------------------------------------------------------------------------------------------------------------------------------------------------

After doing initial enumeration, I look through the results:

- I searched the version of Wordpress (which we got it from nmap scan) and found **many vulnerabilities** -> check out the link: https://www.cybersecurity-help.cz/vdb/wordpress_org/wordpress/4.1.31/ 

And then checked the `/hidden` directory; from this, we get see **three usernames.**

Since we got the usernames, I have improved my  `wpscan` by brute forcing.

And I got the c0ldd password -  which logged in site.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

From the simple research, we see that there is a `Arbitrary file upload` vulnerability. 

WordPress before 5.8 lacks support for the Update URI plugin header. This makes it easier for remote attackers to execute arbitrary code via a supply-chain attack against WordPress installations that use any plugin for which the slug satisfies the naming constraints of the WordPress.org Plugin Directory but is not yet present in that directory.
Source: https://wpscan.com/vulnerability/95e01006-84e4-4e95-b5d7-68ea7b5aa1a8/

***This is win for attacker. And admin should have update the website.***

----------------------------------------------------------------------------------------------------------------------------------------------------------------------








