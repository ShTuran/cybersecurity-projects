![image](https://github.com/user-attachments/assets/b45dd1f2-4446-4507-8e07-b4a4572ffbc5)

Even though it was not useful, the first thing I have found the is reflected XSS vulnerability:

![image](https://github.com/user-attachments/assets/de0cb4e9-a7a8-4881-b6c2-a4f6842b8d98)

![image](https://github.com/user-attachments/assets/b6bb89db-dce3-41af-8ed7-c32076f34d00)

To find the main vulnerability, we was needed the source code {I do not know what happened in the main HTB platform, but I could not be able to find the source code, so I head overed the Github of HTB and find the source code there.}
https://github.com/hackthebox/cyber-apocalypse-2024/tree/main/web/%5BVery%20Easy%5D%20TimeKORP

This is `TimeController.php`

![image](https://github.com/user-attachments/assets/d658da87-4d37-40a5-b263-d41a26b61e82)

This is the constructor:
     `$time = new TimeModel($format); `


where 

TimeModel.php:

![image](https://github.com/user-attachments/assets/f80dd266-22e8-4f75-ba24-e7fe2af9e964)

To get the flag, we need to manipulate $format as `'; cat/flag;# `

![image](https://github.com/user-attachments/assets/e5a44915-d319-4546-bd52-e2d0405890de)





