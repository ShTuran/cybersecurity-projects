First, we need to download the necessary file and extract it using a given password:

`unzip yourfile.zip`

After that, we see that we have only one file, which ends with .bin.

The tool called binwalk might be helpful to analyze the file. To do this, we run:

`binwalk -e firmware.bin`

After extracting the file using binwalk, we get a lot of folders.

We need to find the appropriate credentials to log in to the system. For that, we will use the grep command:

`grep -r -e login`

![username](https://github.com/user-attachments/assets/a01995aa-f441-4ef0-aecb-594fa573e663)

With that, we find the username.

Now, we need to find the password. The find command will help us:

`find -type f -name sign`

![find-the-password](https://github.com/user-attachments/assets/e674328d-e927-41da-8f13-f15b38fe6143)

![find-the-passworde](https://github.com/user-attachments/assets/99aa285b-cdce-42be-b49b-853c873b5307)


After obtaining the username and password, we need to log in to the system:

nc <IP> <PORT>

![login](https://github.com/user-attachments/assets/ca39398e-a918-46c9-b9d1-b045ceb4a7f7)

Once logged in, we use ls to see the flag:

`ls`
