Download the zip and then unzip with the given password.

Description mention that it a `web` challenge:

![image](https://github.com/user-attachments/assets/ae60c711-ce42-49a7-8e50-0c9808400460)

Web page:

![image](https://github.com/user-attachments/assets/a5be2a3d-9b81-4c4d-afd3-a03842b2810c)


I am in `challenge` directory and let's analyze the `app.py`: 

![image](https://github.com/user-attachments/assets/003ef6f8-dc69-4303-9595-cf029d8a375d)

I have tried famous payload `<script>alert(1)</script>` to see if it is indeed working and it did. 

`flag` will be given to us as a alert:

![image](https://github.com/user-attachments/assets/1985ad6d-8350-4d36-a1e1-ff2fe0ca5367)

So, it is worth to check some XSS payload which is not containing `<script>`:

