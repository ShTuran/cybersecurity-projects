Enter the given IP and corresponding port:

![image](https://github.com/user-attachments/assets/abcffc6f-e68d-4e8c-b8c1-1dca9a0614a9)

As always, I tried some default credentials - not successful!

As a 2nd step, I have tried SQLi - not successful!

Since we do not know any username to brute force, it is meaningless.

Without looking the source code, we could not be able to identify underlining technology:

![image](https://github.com/user-attachments/assets/5a1cca32-4906-424b-9717-9dd39ba98520)

After that, I have tried to catch the request to see if something anormal:

![image](https://github.com/user-attachments/assets/fea1a079-5ad2-4e53-a03c-384c5759b1a0)

Nothing seems odd.

Next best step is looking the source code:

![image](https://github.com/user-attachments/assets/04b98314-f2fd-461d-bb90-ea8575ca1a75)

We detected Mongodb

![image](https://github.com/user-attachments/assets/d25fe366-a22c-41ae-8696-74f7414fe8e6)

Flask

![image](https://github.com/user-attachments/assets/305f7cbe-7ead-4416-89b2-809b50a7bc13)

Seems that we can make `content-type` as  json as well.

With that in my mind; we also have Mongodb..

We can try to inject one of the payload from [here](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/NoSQL%20Injection)

We can manipulate - `email` and `password` as something and make that value `not equal` = `something`

Result:

![image](https://github.com/user-attachments/assets/0f392976-3ad6-4c02-9af9-441d4b1aa8ed)

I have forgot to change `content-type`:

![image](https://github.com/user-attachments/assets/35b69783-cbf8-4e44-9e90-85d64bd1a5c7)

Same result.

![image](https://github.com/user-attachments/assets/e8eece75-0dd6-4609-b668-0648888691b1)

So this is not we want; we want to get `flag`, not to directed to `/`

I made silly mistake in this `challenge`  where I should have put `email` not `username`...

![image](https://github.com/user-attachments/assets/978f8552-bc8b-4819-979b-235fc80332d7)









