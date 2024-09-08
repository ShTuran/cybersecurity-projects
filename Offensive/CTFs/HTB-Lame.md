First, started `nmap` scan:

![image](https://github.com/user-attachments/assets/8735bfb6-bd24-4ce8-bd0a-553df8af2b74)

![image](https://github.com/user-attachments/assets/df5db28c-2abf-45f9-9ae8-fac1fb405ee3)

The vsftpd was running on vunerable version; when I searched up, I found the exploit:

![image](https://github.com/user-attachments/assets/619c7ef9-187e-4328-a6d7-629e26355d8c)

I searched on metasploit and run it, but it was not successful.

And logged in to ftp server as anonymous user, but it was empty.

Next up, I found vulnerability realated to Samba

![image](https://github.com/user-attachments/assets/a71be3ce-99b5-481d-9112-e5b201d67360)

Again the exploit was available on metasploit; after setting everyting, it gave us direct root access:

![image](https://github.com/user-attachments/assets/225a27c3-0a11-4987-884d-2c1c26b75a23)



