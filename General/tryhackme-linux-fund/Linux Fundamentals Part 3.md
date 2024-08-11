# Create a file using Nano

- to create a file type nano and followed by 'filename' 

`nano turan`

# Edit "task3" located in "tryhackme"'s home directory using Nano. What is the flag?

To edit a file type `nano task3`, this will open nano editor for task3

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/1d827519-bc1e-4d76-a307-307590e252ba)


# Ensure you are connected to the deployed instance 

- To connect the server use `ssh`

`ssh tryhackme@machine_ip_address` 

#  Now, use Python 3's "HTTPServer" module to start a web server in the home directory of the "tryhackme" user on the deployed instance.

`python -m http.server`

# Download the file http://machine_ip_address:8000/.flag.txt onto the TryHackMe AttackBox. Remember, you will need to do this in a new terminal. What are the contents?

- Note that above IP address is only specific to the user, you need to change it.

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/598abeee-9df1-449c-924e-05ee9d91dbd7)


# Create and download files to further apply your learning -- see how you can read the documentation on Python3's "HTTPServer" module.  Use Ctrl + C to stop the Python3 HTTPServer module once you are finished.

✅

#  If we were to launch a process where the previous ID was "300", what would the ID of this new process be?

- '301', processes increase one-by-one.

#  If we wanted to cleanly kill a process, what signal would we send it?

- 'SIGTERM' , this will cleanup tasks beforehand

#  Locate the process that is running on the deployed instance (10.10.202.248). What flag is given?

- after running `ps aux`:

  ![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/e520b1ac-58e3-49bb-93f4-60fab98e4d81)


# What command would we use to stop the service "myservice"?

- We need to follow this syntax -> systemctl [option] service

-  `systemctl stop myservice`
 
# What command would we use to start the same service on the boot-up of the system?

Again the same syntax, but it says 'boot-up' you have to use enable/disable command, since wanted to start on boot up:

- `systemctl enable myservice`

# What command would we use to bring a previously backgrounded process back to the foreground?

- `fg` will bring back the backgrounded command.


# Ensure you are connected to the deployed instance and look at the running crontabs.

`crontab -l` will list current user cronjobs.

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/a91229c3-2baf-4aee-a40f-1558eaa76329)


# When will the crontab on the deployed instance (10.10.202.248) run?

After running `crontab -e` which is edit mode of crontab:

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/54c71879-a7f3-4153-9af5-d1b4434c5111)

  
# Look for the apache2 logs on the deployable Linux machine

`cd /var/log/apache2`

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/e28c2000-2d48-4c4f-968f-ff334a02e509)

  
# What is the IP address of the user who visited the site?

 ![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/f16960a7-0a84-4f5c-b8fa-34271c167b8f)

it also answers the last question
 
# What file did they access?

- 'catsanddogs.jpg'
