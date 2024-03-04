---
layout: post
title: Things to do after renting a VPS
nav_order: 2
parent: Linux Lighthouse
---
# Things to do after rent a VPS
So I heard you are ready to spin up a Cloud VPS? 
No problem. But you got some setup to do, such as security and automatic updates.

I'm using Debian as the guide here. If you are using different distros, commands are different. 

- [Users and sudo](#users-and-sudo)
- [Disable Root SSH](#disable-root-ssh)
- [Firewall ports](#firewall-ports)
- [Change SSH service port](#change-ssh-service-port)
- [Unattended Upgrades](#unattended-upgrades)
- [At the end](#at-the-end)

## Users and sudo
Linux is the kind of Operating system that will do what you exactly want them to do. So don't run commands in root and don't use root account as your account. Secondly, when you log in as root, every application you run will run with root privileges. This might lead to apps deleting files, creating files in different places that they shouldn't. And it will break your system. 

Most VPS company will set the machine up as root and give you the freedom to do anything. So we are going to create a user, give it superuser privileges. 
```
adduser yourusername # Add user yourusername
usermod -aG sudo yourusername # Put yourusername to sudo group
```
Now you have your own user! `exit` the root user and login in as your new user. 

## Disable Root SSH
We are going to disable the root user from login using ssh. To ensure more security and reduce attack surface. 
I'm using vim, you can use nano or other text editor. 
```
sudo vim /etc/ssh/sshd_config
```
When editing the system, configure files needs superuser privileges.  
In the config file, find the line `PermitRootLogin yes`, and replace the word `yes` with `no`. 
![a72b9315090d1ac9020ee4f88c8b2ff0.png](/assets/a72b9315090d1ac9020ee4f88c8b2ff0.webp)
Save the file and restart ssh.
```
sudo systemctl restart sshd
```

## Firewall ports
Here we are going to reduce more attack surface by limiting Firewall ports.  
I use Uncomplicated Firewall (ufw) on my Debian box.  
Install it by using `sudo apt install -y ufw`. 
```
sudo ufw status
```
This command will tell you if your firewall is active and list out all the ports that are open. 
![a1a25ea15a3be36e5fb16d599c23b4b3.png](/assets/a1a25ea15a3be36e5fb16d599c23b4b3.webp)
For me, I use this server as a web server and reverse proxy on it. 

To ensure security, I want to close a port I no longer needed.  
For example, I want to close port 8448:
```
sudo ufw deny 8448
sudo ufw reload
```
Always close ports you are no longer needed.  
Don't forget to reload your firewall after setting it up. 

## Change SSH service port
Secure Shell uses port 22. There's nothing wrong with using this port, but it is too common. It's really easy to determent if your machine is using SSH or not. The best practice is to change it to another port. 

Let's open up SSH's config file again. 
![4b9e1e28a98289be53edc3ab082565af.png](/assets/4b9e1e28a98289be53edc3ab082565af.webp)
Change this port to any ports higher than 3000. 

Make sure you have that port opened on your firewall, and restart both your SSH service and your firewall. 

## Unattended Upgrades
This is the software that automatic updates your machines when you're using Debian based systems (Ubuntu, etc...)  
[AutomaticSecurityUpdates](https://help.ubuntu.com/community/AutomaticSecurityUpdates)

If you are using RHEL, CentOS, AlmaLinux, RockyLinux or Fedora.   
[DNF Automatic](https://dnf.readthedocs.io/en/latest/automatic.html)  
[Fedora Wiki AutoUpdates](https://www.fedoraproject.org/wiki/AutoUpdates)  
If you are using openSUSE  
[YaST Online Update](https://en.opensuse.org/YaST_Online_Update)

The config file `/etc/apt/apt.conf.d/20auto-upgrades` can be easily created by run the following command as root: 
```
sudo dpkg-reconfigure -plow unattended-upgrades
```
![69a9a2fb9e89dd91a3661e30ddb9b03b.png](/assets/69a9a2fb9e89dd91a3661e30ddb9b03b.webp)
Select `Yes` and It should generate the config files automatically. 
Now we need to edit the config file for the things you want to automatic updates. 
```
sudo vim /etc/apt/apt.conf.d/50unattended-upgrades
```
![dc8b2631c664f924196a7d39e45b9035.png](/assets/dc8b2631c664f924196a7d39e45b9035.webp)
There are some lines you need to uncomment, for example 
`"origin=Debian,codename=${distro_codename}-updates"`.  
Uncomment this line will download every new packages, which is what I want my system to stay up to date all the time.  
You can also just only uncommon the `"Debian-Security"`. This will only update for security rollouts. 

There's nothing wrong with stay on older packages, it will bring you the best stability. But I wanted my system to be up-to-date. It is all personal preference.  

![9739e5a649c89fb3bf0810349b84f457.png](/assets/9739e5a649c89fb3bf0810349b84f457.webp)
Here are some line you can also uncomment:  
`Remove-Unused-Kernel-Packages`  
This will remove the old kernel that is no longer needed.  
`Remove-New-Unused-Dependencies`  
This will remove unused dependencies if a package updated and no longer needed.  
`Remove-Unused Dependencies`  
This will remove unused dependencies. 

`Remove-New-Unused-Dependencies` and `Remove-Unused Dependencies` works the same as command `sudo apt autoremove`

Last but not least, let's check if we have done it correctly. 
```
sudo cat /etc/apt/apt.conf.d/20auto-upgrades
apt-config dump APT::Periodic::Unattended-Upgrade
```
![4316a50179e1fe474a1774f5f492d4df.png](/assets/4316a50179e1fe474a1774f5f492d4df.webp)
Both commands should return something like `Unattended-Upgrade "1";`. This indicates that your configuration is correct. 

## At the end
Even tho we have already set up the automatic updates, I still highly recommend you log in from time to time to check the SELinux log if anything is not running correctly. 
Thanks for reading! 

<script src="https://utteranc.es/client.js"
        repo="Colgrave34/Colgrave34.github.io"
        issue-term="pathname"
        label="Comment"
        theme="github-dark"
        crossorigin="anonymous"
        async>
</script>