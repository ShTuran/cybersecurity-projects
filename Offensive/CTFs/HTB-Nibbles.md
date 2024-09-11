# Nibbles

Let's start our nmap scan:

![image](https://github.com/user-attachments/assets/cba7f845-3aa4-4fd1-b433-b9c4418923e4)

Website looks so:

![image](https://github.com/user-attachments/assets/93b36e4d-03af-49e4-b614-adbfc1453f05)

Nothing interesting.

After looking the source-code:

![image](https://github.com/user-attachments/assets/9fc0680c-7c52-4778-917d-4b1fb45bcbe7)

`/nibbleblog`:

![image](https://github.com/user-attachments/assets/a07f38a6-353d-467b-9e76-3607cbd79b49)

Quick search showed that nibbleblog has some vulnerability:

https://packetstormsecurity.com/files/133425/NibbleBlog-4.0.3-Shell-Upload.html

Even though, I am not sure about the version of nibbleblog, it is worth to try it;

Poc:

![image](https://github.com/user-attachments/assets/3c212ce0-a02e-43bb-b6b3-39de822c9b85)

We see that there's `/admin.php`:

![image](https://github.com/user-attachments/assets/16d18c12-9539-4ceb-a479-11f2e8af0978)

Website has blacklist, so attention to guesses of password; I have used `hydra` and blocked, restarted the box (do not make that mistake)

Default credentials, `admin:admin`, `admin:123456`, ... I have searched for credentials did not find anything.

So, it is guess game for me. 

`admin:nibbles` is the one.

Even though, we have a PoC at hand; it is worth to try metasploit as well, to see if there is a ready exploit for it already.

And indeed, we have; after setting everything we got a `shell`.

![image](https://github.com/user-attachments/assets/37871527-4de9-4a85-895b-77f090aaf1e0)

**You can get user flag in appropriate user's home directory**

































