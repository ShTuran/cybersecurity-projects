Result of nmap scan:

![image](https://github.com/user-attachments/assets/e2c679d0-382e-4215-8bbf-9f740207f8f2)

Directory enumeration:

![image](https://github.com/user-attachments/assets/2a998c8e-4e6e-40a3-8819-b38724b1c4a0)

Subdomain enumeration:

![image](https://github.com/user-attachments/assets/6e46c94d-4b96-419d-9bf9-26b066b6e24c)

Website:

![image](https://github.com/user-attachments/assets/0ae315b4-d55c-4f91-9192-7828c424e9e8)

There is not so much to do in the website.

Subdomain:

![image](https://github.com/user-attachments/assets/b0aef59d-d4d6-4a7b-bfae-20632fca15a5)

I have directly searhed for default credentials:

![image](https://github.com/user-attachments/assets/04d8779d-d266-4943-8124-73aa19cd963c)

Entered:

![image](https://github.com/user-attachments/assets/cb126f76-07cf-4e22-9d17-6a522737466a)

Searched given information for exploatation:

https://github.com/nikn0laty/Exploit-for-Dolibarr-17.0.0-CVE-2023-30253

![image](https://github.com/user-attachments/assets/ce326bf4-9548-4276-b43d-e0e1ff850ac5)

Implementing given instruction:

![image](https://github.com/user-attachments/assets/90a741fd-3878-41de-976a-a734e73fb765)

![image](https://github.com/user-attachments/assets/9daa3e2d-2369-4e82-ba85-33706f60123b)

There is no specific thing to do here. And the most common thing is looking for `conf*` files which contain passowords.

Let's search for that file:

![image](https://github.com/user-attachments/assets/fe791df8-75ee-4f15-980e-0a1dd90415be)

More specific:

![image](https://github.com/user-attachments/assets/beb161bd-d4bf-4bf2-85a3-f2e727dd64a4)

Our file:

![image](https://github.com/user-attachments/assets/8274bc06-10dc-415c-8a9d-dd0a5ca00435)

![image](https://github.com/user-attachments/assets/5d3fc27a-a67b-4570-8306-cf2778624f08)

This is my be our user `larissa` password as well (password reuse):

And yes it is; we are right with our guess.

We `ssh` into:

![image](https://github.com/user-attachments/assets/9d343dad-238f-49b8-acd1-14c46a65b34a)

Privesc:

![image](https://github.com/user-attachments/assets/4a9662ab-db05-439a-950d-4b84632539da)

![image](https://github.com/user-attachments/assets/b28c69bb-08bc-43ba-aa88-5e191b2242d0)

![image](https://github.com/user-attachments/assets/400c0d04-22b1-40c3-aeef-0173272bc1de)

This is the exploit, will give us root access:

https://github.com/MaherAzzouzi/CVE-2022-37706-LPE-exploit

After saving the code into a a file and run it:

![image](https://github.com/user-attachments/assets/834d458f-4d0d-4b55-9a01-e602e36e27ab)








