 Nmap result:

![image](https://github.com/user-attachments/assets/09c1f04b-773d-4a34-ac1e-cf5786351ddd)

Web interface:

![image](https://github.com/user-attachments/assets/6b40d867-46e1-45fb-a9e5-467466a1705c)

Gobuster result:

![image](https://github.com/user-attachments/assets/c04a8236-64a9-4ea4-be14-04edf8204caa)

Tried to access `Manager App` and found some credentails:

![image](https://github.com/user-attachments/assets/8ec32832-7186-43fc-a451-e58066fa6d3b)

And we managed to get acess:

![image](https://github.com/user-attachments/assets/a9b2a4be-4ab7-41cf-995e-5e7e5c4d5e88)

We have a place to upload something:

![image](https://github.com/user-attachments/assets/e6a73263-30e1-4b4a-a2de-054222220ea2)

We can potentially upload a shell and get a reverse shell. But our uploaded file must be in a `.war` format. 

We need to build the shell and put the listener; for that I'll use `msfvenom` and `metasploit`:

It is worth to note that, we got server information as well:

![image](https://github.com/user-attachments/assets/3a7500e5-99a7-43f3-a587-02a1682ead0b)

Create the payload:

![image](https://github.com/user-attachments/assets/59249dc8-f4b1-466b-876c-647fb203e1da)

Create the listener:

![image](https://github.com/user-attachments/assets/8076090d-682d-4810-8d7e-cbef22d870c1)

Upload to web server:

![image](https://github.com/user-attachments/assets/6957b320-4060-49f7-a635-d917b0bb7cbd)

Request the payload:

![image](https://github.com/user-attachments/assets/1c6c3c11-6823-455a-b9e7-133319c9a064)

we did not get the shell


Catch the shell:

Get the flags:



