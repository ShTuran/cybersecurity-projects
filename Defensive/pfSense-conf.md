# Configuring pfSense and familiarizing myself with the system 
I have use this [video](https://www.youtube.com/watch?v=RiF2pEAtUVQ&t=752s)


## Features:

- **open source** firewall, community support (limited official support)
- network security and **traffic management**
- it can depyloyed as a firewall, router, VPN endpoint, DHCP server, intrusion prevention/detection (overall, enhance the network security) and with that being said it shows how pfSense **flexible, scalable**
- **user friendly** web interface
- stability and reliability
- monitoring/logging and reporting
- suitable for both small-scale and enterprise-level deployment

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Installation

Accept it:

![image](https://github.com/user-attachments/assets/eff8ef0a-e60a-4204-b23f-ff38628411ae)

I just chose install:

![image](https://github.com/user-attachments/assets/b79dbcc8-514b-4155-89eb-af0bfcf6c9cd)

Auto (ZFS):

![image](https://github.com/user-attachments/assets/d9b97220-9b4d-4f6e-9d4b-dc7191fda352)

I have changed nothing, just install it:

![image](https://github.com/user-attachments/assets/7ef72e28-54b5-44df-a962-bbe3f77b495d)

Because of I install into virtual machine, chose first one:

![image](https://github.com/user-attachments/assets/cf4219f0-75d5-44d3-b480-b0ad44f1c2d6)

OK:

![image](https://github.com/user-attachments/assets/dbdb3c6f-1741-4c70-81db-89efad160fc8)

If after that it says: not enough disk selected, just click space bar (which I have encountered during the installation) - https://www.reddit.com/r/PFSENSE/comments/hen522/zfs_disk_selection_not_possible/


Yes:

![image](https://github.com/user-attachments/assets/5ad7a6ce-cdda-496c-b4c5-797fa93e4838)


![image](https://github.com/user-attachments/assets/53b63608-d687-42e8-a18c-41febfda5f90)

When we are dealing with pfSense we need 2 network interface:

![pfsense(1)](https://github.com/user-attachments/assets/adca3af2-8990-4a98-8de8-2948c7456215)

Please do not judge my drawing ability :)

![image](https://github.com/user-attachments/assets/e9ec12de-581c-4fb2-8ec9-ca2052394fe9)

In here, type `a` for auto detection:

![image](https://github.com/user-attachments/assets/b5b0bea3-7d30-4200-a264-b5c57b606930)

Press enter:

![image](https://github.com/user-attachments/assets/1d6541cb-33fb-4bbd-87e9-48e6cd56700c)

And 2nd interface which is em0:

![image](https://github.com/user-attachments/assets/e89781c5-abe2-444e-9d43-a39e4aa6ccb9)

We have finished the interfaces (which is 2), that's why press enter:

![image](https://github.com/user-attachments/assets/a94d5ce6-2ff2-4242-a295-29fac14a20cd)

type `y`:

![image](https://github.com/user-attachments/assets/81f296ea-112e-4c0c-a217-b7bd49e7d373)

And:

![image](https://github.com/user-attachments/assets/751570e4-3feb-431f-bcec-02e80cd0587d)

If you do not see the LAN interface as me, just 4 `reset to factory` and `y`, this solved my problem:

![image](https://github.com/user-attachments/assets/787f704a-8579-4b8d-aad7-6c864489847e)


If you want to get web interface (ofc, you want) - do this steps: 
I struggled most in here:

![image](https://github.com/user-attachments/assets/5e23fa3d-d944-4ccc-9b0e-563f7c08da26)

![image](https://github.com/user-attachments/assets/f6517da9-7ff8-4389-91d9-8e1d5aee59b3)

![image](https://github.com/user-attachments/assets/c73bcc7e-a1d2-492d-a6d4-4bbd23ac765c)

![image](https://github.com/user-attachments/assets/1b8ce9c0-9894-4de0-a575-ba583c059a8e)

And add `192.168.1.x` ip address here, because our default LAN address is `192.168.1.1`, so our computer should be able to talk with `pfSense` which is on VM

![image](https://github.com/user-attachments/assets/2e4af60c-9e30-4963-b5a1-58d5fbe074b6)

Default credentials: ***admin:pfsense***

![image](https://github.com/user-attachments/assets/34cf3b2e-ef65-41d0-89f1-910b3a745e30)

If you use this not for lab, change the default creds:

![image](https://github.com/user-attachments/assets/0db247f9-4dcc-4411-bf84-e4b9d75978e5)


![image](https://github.com/user-attachments/assets/390b62cc-1400-4ef7-9723-5082baac65e1)

I have changed nothing up until now, just clicked `Next` button.

Finally:

![image](https://github.com/user-attachments/assets/811d1fed-d439-4dea-b501-89a3e5d91be5)

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Web interaface

On the next page we got system info:
![image](https://github.com/user-attachments/assets/40b9060b-72d7-46b5-b5a5-3adcae53eaf9)

System > User Manager 

You can add user from there and adjust the necessary info:

![image](https://github.com/user-attachments/assets/c868ee63-e60d-44d6-bdda-cef7d2d6e39e)

![image](https://github.com/user-attachments/assets/ec43abb7-2197-4069-8f6c-7982362b553d)






