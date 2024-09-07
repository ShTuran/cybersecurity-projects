When I see login page, first thing come into my mind is SQLi; so when I put `'` in a username i got:

![image](https://github.com/user-attachments/assets/15a69154-77a4-4b86-957f-9613b7c36608)


We need to capture the request and add `*` to username to tell `sqlmap` where to add the payloads

![image](https://github.com/user-attachments/assets/f2346a76-ad5d-4961-8816-05a7d1c54557)
