# SSH Keys

## Why SSH Keys?
You are probably familiar with using a username and password to login to a website or other account. 
You can do this with a remote server too. However, passwords have a lot of disadvantages. 
Many people try to memorize passwords, which leads to them choosing a password that can be easily guessed or broken by an attacker. 
No matter how good you think your algorithm is for choosing a password you can remember, 
a machine can be programmed to guess your password very quickly, and your algorithm will make it easier. 
People also reuse passwords across multiple sites, so that if an attacker breaks a password they can compromise multiple accounts. 
You also need to type a password (or copy and paste it from a password manager) each time you use it.

For accessing important assets, such as remote servers and GitHub, we will show you how to use SSH keys. 
An SSH key uses strong cryptographic standards, meaning an attacker would need billions of years to break your key. 
In addition, you can configure SSH keys so that they are unlocked when you login to your account, 
so that you can avoid typing a password each time you use it. 
This is a win-win for you: much better security plus improved convenience.

## A Brief Introduction to Public Key Cryptography
SSH keys use public key cryptography. You will create both a public key and a private key. 
Your public key, as the name suggests, is public -- you can safely give this to any person or system. 
Your private key should remain private. Ideally, you should protect it with a password, as described below, 
so that if it is stolen, there is an extra level of protection that prevents someone from using it.

The public and private key have a special, mathematical relationship. 
Anything you encrypt with your private key can be decrypted with your public key. No other key will decrypt it. 
Likewise, anything someone encrypts with your public key can only be decrypted with your private key.

Public key cryptography can be used in a variety of ways, but we will be using it for 
authentication -- meaning you can prove your identity to another system. Here is how that will work:

- You create a public and private key pair.
- You store your public key with a service, such as with a Digital Ocean server or with GItHub.
- When you want to login, you present your public key to the service.
- The service asks you to prove you own that public key by having you encrypt something with your private key.
- The server will decrypt that thing with your public key, thereby proving you own the associated private key.
- The nice thing about this is that it is completely automated once you set it up. 
Your ssh program just needs access to your private key, and it will do everything for you.

## Creating an SSH Key
To create your SSH key, you will use a program called ```ssh-keygen```. 
This will generate your public and private key pair and store them in a directory called ```~/.ssh```. 
Normally, the public key will be called ```id_rsa.pub``` and the private key will be called ```id_rsa```. 
Be sure to use a strong password when asked for one. 
I recommend a long phrase or a [correct-battery-horse-staple password](http://correcthorsebatterystaple.net/).

If you are using Windows, remember that you will do this using Git Bash.

## Aside: Good Password Hygiene
When you have to use passwords, such as on most websites, be sure to choose a long, random password to avoid attackers guessing your password and breaking into your account. Use a password manager to remember it and then copy and paste it or autofill it each time. Good password managers include 1Password, LastPass, and DashLane.

## Fixing your SSH system
If you mess up, try deleting your ~/.ssh folder on both your local and remote machines and going through the tutorial again. Here is a [Mac-specific tutorial from GitHub](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) that covers the same material as above.
