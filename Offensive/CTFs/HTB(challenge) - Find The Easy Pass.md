Downloaded the file and:

![image](https://github.com/user-attachments/assets/f4e06dcf-0480-4775-921e-8ea5508453c2)

It is Windows exe.

So, in order to execute `.exe` file on Linux I have used `wine`:

![image](https://github.com/user-attachments/assets/c2c5ea81-98cb-4e81-a4d9-3d2227e23db4)

We need to find the password.

I'll use `Ghidra`:

`Ghidra - A software reverse engineering (SRE) suite of tools developed by NSA's Research Directorate in support of the Cybersecurity mission`

When we type wrong password:

![image](https://github.com/user-attachments/assets/aea7d05c-8445-4dbb-ab7d-c2be4cc1002f)

This is useful, because we will use it;

With search functionality:

![image](https://github.com/user-attachments/assets/eec681ad-ed7c-483b-8e97-ade3d350d28f)

![image](https://github.com/user-attachments/assets/ace2159c-50e5-4949-b4e2-9c3688b4359e)

Above that, we see some letters: `fortan!` - I have tried for password but it is not.

![image](https://github.com/user-attachments/assets/bc9da917-7e5c-4623-8179-7a69cc562c91)

When I highlight the function:

![image](https://github.com/user-attachments/assets/2e480985-f0e3-47a8-a28a-7b25dd91f6f9)

Password: `fortran!`








