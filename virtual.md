# Virtual Private Servers
You can create a Virtual Private Server on several different Cloud Platforms. 
As shown below, a powerful physical server can run a set of virtual servers, 
each using some of the hardware resources available on the physical server. 

When you purchase a server, you get access to a server that looks and runs like it is your own machine. 
You have root access on the machine and an IP address, and can otherwise configure the machine as you desire. 
It is inexpensive to purchase because it does not have dedicated hardware, but instead shares the hardware of the physical machine.



Root Access
When you create your server, you will have root access on it. This means that you are the administrator of the machine. You can install whatever software you want and will need to manage the machine yourself.

You will want to be careful! For example, within minutes of you creating your virtual machine, someone on the Internet will likely try to break into it by guessing your root password. This is not an exaggeration, it happens regularly. So you should be sure to choose a very strong root password. Digital Ocean will create a password for you that should be fairly strong.

Having root access also means you can easily mess up and delete your code, crash the machine, and so forth. For this reason, we will show you how to always keep  your code in a code repository at GitHub. This way, even if your server gets completely messed up, you can always restart it or create a new one, load your code, and pick up where you left off.

SSH
To access your server, you will use a program called ssh. You should do this from the command line.

ssh root@45.55.164.105
This will connect you to the machine and ask you for a password. Since you specified the root account, you will need to supply the root password, which Digital Ocean should give you when you create the server.

You will need to supply the IP address for your machine, not the one in this example.

 

Your Own Account
A good practice is to setup a separate username and password to access your machine. For example, if your name is Sarah, you could setup an account with the username sarah and a password of your choosing. As with the root account, be sure this is a very strong password. A good practice is to choose a random password and then store it in a password manager. Alternatively, create a password by using multiple, unrelated words, like "correctbatteryhorsestaple". Once you begin using your own account, instead of the root account, then you will be connect to the machine this way:

ssh username@45.55.164.105

Supply the password you chose. You will now be working with files in your own home directory, e.g. /home/sarah.

sudo
At times, you will need to take certain actions that require root access, such as installing or configuring system software. To do this, you will use the sudo command. su stands for "super user" so sudo means "do this using my superuser privileges". We have shown you in a previous activity how to give yourself super user or sudo privileges when creating your account. To use sudo, you simply preface any command with sudo, such as:

sudo ls /var/log/nginx/
