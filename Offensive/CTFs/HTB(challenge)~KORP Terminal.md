![image](https://github.com/user-attachments/assets/782311f0-3e63-4def-8d29-971eb90f77d4)

When I see the login page, I checked default credentials - not worked

![image](https://github.com/user-attachments/assets/e81a1fc0-c570-40da-a389-19556a9d552f)

2nd thing is to check source-code; nothing valuable;

and 3rd is: SQLi; most of payload did not work but `admin'` is (error-based)

![image](https://github.com/user-attachments/assets/15a69154-77a4-4b86-957f-9613b7c36608)

We need to capture the request and add `*` to username to tell `sqlmap` where to add the payloads (it works without `*` also)

![image](https://github.com/user-attachments/assets/f2346a76-ad5d-4961-8816-05a7d1c54557)

After that, I put that request into a file and give it to `sqlmap`:

![image](https://github.com/user-attachments/assets/eeec4355-8a41-47a8-a7f1-f7daa2178f37)

since I got the `401` error, I needed to ignore them.

![image](https://github.com/user-attachments/assets/6fd84fa5-c298-4d35-b9cc-610b4608dd8f)


![image](https://github.com/user-attachments/assets/7035406a-3b1b-4a1e-a36c-94d50583adc0)

![image](https://github.com/user-attachments/assets/4d47fafa-c96b-4567-9aa8-7e4485e77048)

![image](https://github.com/user-attachments/assets/eb8f35d3-c7f1-4d27-b806-46c1279b2f91)

![image](https://github.com/user-attachments/assets/249d6702-170f-42ab-bf22-30815cb81be6)

Next up, we need to crack the password, below we used `john` and it gave us the password to login as admin

![image](https://github.com/user-attachments/assets/3d160df5-60a1-4e60-b381-38466e8789ba)







