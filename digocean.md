# Setting Up a Digital Ocean Server

1. Follow the [how to create your first droplet tutorial](https://www.digitalocean.com/community/tutorials/how-to-create-your-first-digitalocean-droplet) 
to create a remote server using DigitalOcean. They call their servers "droplets". 
The $5/month version will be fine. Use a Ubuntu image so you want to follow along with our advice this semester. 
Skip Step 7 of the  tutorial (Select SSH keys).  
You will setup SSH keys later according to the directions on this page. 
You can get the server for free if you sign up for [github backpack](https://education.github.com/pack).  

2. At the conclusion of this step, verify that you can use the username root and the password that was emailed to you to 
3. login to your Digital Ocean server. You can do this with

```
ssh root@45.55.164.105
```

Be sure to substitute your own IP address.

4. Follow steps 1-3 on the [initial server setup tutorial](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04) 
to create a non-root user with sudo privileges.  
Use your non-root user to log in so you don't do everything with root privileges (which can cause your server to be less secure).

5. At the conclusion of this step, verify that you can use the your own username and password to login to your Digital Ocean server. You can do this with

```
ssh username@45.55.164.105
```

Be sure to substitute your own username and IP address.

You will do everything on your Digital Ocean machine with this username so keep track of it. 
When you need to do something that requires root access, you will use the sudo command. 

## Fixing Your Server

If you mess something up with your server and you are unable to use ssh to access it any more, you can use this guide [https://www.digitalocean.com/docs/droplets/resources/console/](https://www.digitalocean.com/docs/droplets/resources/console/) to regain access to your server. It shows you how to access the console for your server, which is like having a monitor and keyboard plugged into your virtual machine. You can do everything you would normally do with your root or user account, fix things up, and then go back to using ssh. 
