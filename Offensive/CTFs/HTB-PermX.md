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

![image](https://github.com/user-attachments/assets/f3f10a2e-2b27-4d1f-a8a2-b9a27ff71ca3)

Opening listener:

![image](https://github.com/user-attachments/assets/ec4e96b2-2ddb-4838-acba-4dd2616bade1)







