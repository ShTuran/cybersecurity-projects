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



