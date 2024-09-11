***The box  completed 2nd time (because I forgot to take ss)***

Result of `nmap` scan:

![image](https://github.com/user-attachments/assets/94230a51-1a0e-445d-a5fa-8309c3aca4d8)

Result of `gobuster`:

  diretory listing

![image](https://github.com/user-attachments/assets/821f6edc-c7c0-44a7-833b-46f26840388c)

Result of `gobuster`:

  subdomain

![image](https://github.com/user-attachments/assets/b7d2933a-8ba3-4748-bf8a-2cd8823221f4)

Visited `lms.permx.htb`:

![image](https://github.com/user-attachments/assets/d78192be-9ea2-4b20-aee6-6c848c9e9b10)

Tried to find default credentials and some easy password - but was not successful.

After researching, I found there is RCE vulnerability, it is worth to try out:

Reference: https://pentest-tools.com/vulnerabilities-exploits/chamilo-lms-11124-remote-code-execution_22949

![image](https://github.com/user-attachments/assets/ec53cd3a-0864-4fb6-8c82-6cd7201ac266)

![image](https://github.com/user-attachments/assets/a53e40d5-2383-497e-9c2b-9851a80bc42e)

And we have very detailed PoC:

![image](https://github.com/user-attachments/assets/e14e57c6-ca72-4404-aace-d0d9e8dd85bd)

Visited the website (some people on the box, already put the reverse shells)

![image](https://github.com/user-attachments/assets/15aadc10-0a3e-4d25-b86d-b2413a74cbd4)

![image](https://github.com/user-attachments/assets/a68add71-bfc4-48e2-9ec7-ebd85f1768c3)

Hitting:

![image](https://github.com/user-attachments/assets/2d6c19b1-c31c-480e-b6c4-099d46c91816)

Opening listener:

![image](https://github.com/user-attachments/assets/ec4e96b2-2ddb-4838-acba-4dd2616bade1)

![image](https://github.com/user-attachments/assets/65265c7a-13e9-4dca-aeb5-b0ab17d8a1a3)

We have successfully completed the PoC steps.

But here we do not have access to user `mtz`'s direcory.

This is where I stucked mostly.

However, as we know that `conf` files contain some password - so it is worth to check them; in case we found a password for a second openn port - `ssh`

Gone to root directory: `/var/www/chamilo/app/config` this is where worthy files greeted us. 

![image](https://github.com/user-attachments/assets/3c3d05e5-4427-4dd8-b0da-dbc78deb39b0)

But we did not find `ssh` pass, what we have found is db_password; still useful.

![image](https://github.com/user-attachments/assets/dd8effb7-4d90-4111-aaa3-9fec320c465b)

One of the main password problem is that people use the same password for a lot of services

This password indeed resued for `ssh` as well:

![image](https://github.com/user-attachments/assets/91944be8-ccd8-49ba-9274-31d1bd847db5)

As always we check user sudo permission:

![image](https://github.com/user-attachments/assets/64189895-3694-4ad0-8f61-8bb07a765be9)

This file allow us to change permission of any file within `mtz` home directory.

![image](https://github.com/user-attachments/assets/3213798d-7839-43c7-a978-e6936d78e94b)

What can we do here?

If we give permission to `sudoers` file and edit it; we can escelate our permission to root.

Symbolic link to `sudoers`  file

![image](https://github.com/user-attachments/assets/53ce8329-5d64-48b2-9c02-0079a2598260)

Giving necessary permission and editing file (as root to `mtz`):

![image](https://github.com/user-attachments/assets/f3496f34-c52e-4918-8ade-af077386dfff)












