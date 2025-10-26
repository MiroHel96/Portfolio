# My personal portfolio

## In this file I document basic steps for my portfolio. 

This document can be used for reference, when building your own portfolio. This document is not meant to be a tutorial. It is reference for myself if I need to change anything or come back to check what I have done previously.

### Table of contents

1. Virtual Machine (Optional)

2. Hosting a server from Upcloud

3. Securing Server and opening ports
   - Install UFW
   - Lock root

4. Installing Apache2 to Linux

5. DNS records and domain name which points to your server (Name Cheap)

6. Creating a virtual host to show my website.


## Virtual Machine

I had already installed virutal machine to my pc. My main purpose Is to use it to control my Upcloud server. The virtul machine was used to generate SSH-key for Upcloud. 
Instructions for SSH-key generation can be found from here: [Generate SSH key](https://www.ssh.com/academy/ssh/keygen**).

After generating SSH-key I could set it for UpCloud and securely remote login in to my server. 

## Hosting a server from Upcloud

I will be creating a simple portfolio, therefore I do not need great amount of power for the server. 
The following specs should be more than enough, I can later scale my server if needed.

Tecnical Specs:
- Location `Helsinki`
- Plan includes `1 core CPU`, `1GB of Memory`and `20GB of Storage`
- Backups `Not included`, I will make physical copy and store other backup to cloud.
- Operating system `Linux`, best for hosting due to minimal resource needs.
- Network use public IP addresses
- Login Method `SSH`, for security reasons
- Hostname and Servernames, for security purposes not included in document.

<img width="1193" height="963" alt="image" src="https://github.com/user-attachments/assets/8e3db832-a3d8-444c-8372-57afa51a2ff3" />

<img width="851" height="732" alt="image" src="https://github.com/user-attachments/assets/fdc933dd-17cc-4655-838a-6b7deba3da4e" />

<img width="886" height="1216" alt="image" src="https://github.com/user-attachments/assets/5905da38-b1e1-42e0-9ab4-d4456132de68" />

<img width="869" height="632" alt="image" src="https://github.com/user-attachments/assets/ee8f14f5-1e50-4f13-a04a-b67f6e8050b1" />

<img width="834" height="403" alt="image" src="https://github.com/user-attachments/assets/f3318121-f899-4f1d-a6fb-5ef358ba6c9c" />

## Securing Server 

After generating SSH-key and successfully connecting to my server I installed the following packets to make my live a bit easier: 
- `micro`
- `bash-completion`
- `openssh-client`
- `wget`
- `curl`
- `ufw`

### Locking root account 

I used the following website for reference [Terokarvinen.com - Linux Palvelimet 2025 Syksy](https://terokarvinen.com/linux-palvelimet/#h6-salataampa).

Next I created new user `miro` using `sudo adduser miro`, added it to the sudoers group with command `sudo adduser miro sudo`. Next I copied root -user settings to my account and modified files permissions with commands `sudo chown -R miro:miro /home/miro/`

After Creating the account I tested connetion and sudo permissions with my main account. Everything worked, I contuinued to lock root user so it could not be exploited. I used the following commands `sudo usermod --lock root` and `sudo mv -nv /root/DISABLED-ssh/`.


## Dns records and domain name 
