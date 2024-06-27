---
layout: post
title: PufferPanel Makes Your Minecraft Journey Easier
date: 2024-06-23
category: linux-lighthouse
---
![eb7e4f405901458e80a9569d6bd8f6fa](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/eb7e4f405901458e80a9569d6bd8f6fa.webp)  

I remember a few months ago, friends suddenly wanna play some Minecraft, but the price of MC server hosting was not kind.  

I'll post some photos for the pricing.

Minecraft Realms is the official server hosting service. The Java version is $7.99 per month...

![18fb94a49b3e44609e637e4eb4775c43](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/18fb94a49b3e44609e637e4eb4775c43.webp)

Bisect and Apex are both two companies that advertise pretty aggressively, and 4 GB of memory is around $10 per month.

![d20069d061cc445dbbc2a0b88bc75979](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/d20069d061cc445dbbc2a0b88bc75979.webp)

![d859259deebd43c8972248041f73b68c](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/d859259deebd43c8972248041f73b68c.webp)

For a few students still in college, pocket money is just enough for food and rent. Renting a server just for 2 or 3 months is pretty unnecessary.

Then I thought I'd just get an old computer and run the server myself, which has more than 4 GB of RAM.

While looking for a web interface for the server, I found [PufferPanel](https://www.pufferpanel.com/), which is an open source game server control panel. it is the most clear and easy to use game server panel I have tried in my opinion. Not just Minecraft, it also supports ARK, GMod, Palworld, Terraria and Zomboid.  
Game support list: [https://github.com/pufferpanel/templates](https://github.com/pufferpanel/templates)

![200de389e976f65034db0fdf2c2d96f2](https://docs.pufferpanel.com/en/2.x/_images/serverlist.png)
Image source: [https://docs.pufferpanel.com/en/2.x/featuretour.html](https://docs.pufferpanel.com/en/2.x/featuretour.html)
> dumbproof game server in my opion.

This guide uses Linux as the OS, [Debian](https://www.debian.org/) as the distro, and skips all server preparation work (SSH login setup, adding server users, system updates, and automatic updates).  
Other distributions can be installed theoretically, but certain steps will be different.

## Java
Let's first make sure of the Java version. Depends on the MC server version, Java version's requirements are also different.

|MC Server Version|Java Version|
|-|-|
|Minecraft 1.17|JRE 16 or newer|
|Minecraft 1.18|JRE 17 or newer|
|Minecraft 1.20.5 or newer|JRE 21 or newer|

> Althogh server can run on older version of Java, but newer version will bring more bug fixes, stabiliaty, and performance improment.

Sourced from the [Official Wiki](https://minecraft.wiki/w/Server/Requirements#server_requirements)

### Different between JRE and JDK
You will find 4 Java packages when you search in the repo.

![25a0c50b7121dc2163cbea9d8280c56b](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/25a0c50b7121dc2163cbea9d8280c56b.webp)

JRE is Java Runtime Environment, is mainly for running Java software. While JDK is a toolkit for developing Java programs.  
Headless is without a graphic interface.  
jre-headless is perfect for running a Minecraft server. Of course, if you already have JDK, there is no need to uninstall, JDK includes JRE.

### How to check Java version
In your command line:
```bash
java -version
```
This will output your current Java version

![31cbe63874f3c05c317d18ad77e1b117](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/31cbe63874f3c05c317d18ad77e1b117.webp)

## Installation
Installation will use Java 17 as an example.
```bash
# Add PufferPanel repo to your package manager
curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh | sudo bash
# Checking updates
sudo apt update
# Install Java 17 & PufferPanel
sudo apt install openjdk-17-jre-headless pufferpanel -y 
```

### Firewall Setup
```bash
# Allow PufferPanel web protal connection
sudo ufw allow 8080/tcp
# Allow Minecraft connection
sudo ufw allow 25565/tcp
# Enable ufw firewall
sudo ufw enable
# Reload firewall
sudo ufw reload
```

### Add a PufferPanel user
```bash
sudo pufferpanel user add
```

![27350f155c147ed13bc505072f4f24bf](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/27350f155c147ed13bc505072f4f24bf.webp)

PufferPanel will ask you about user information and also ask if it's an administrator.  
Email is mainly for login, it can also be used for [notification](https://docs.pufferpanel.com/en/stable/guides/email.html). It requires an email supports SMTP, which I personally haven't tried and can't say much about.

### Configure Systemd service
```bash
sudo systemctl enable --now pufferpanel
```
If all goes well, you will see PufferPanel when you open `http://<server ip>:8080`

![a7af0390b865390544f1337aeb4920ca](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/a7af0390b865390544f1337aeb4920ca.webp)

## Server Setup
PufferPanel uses Templates to set up and launch servers, this includes the server name, port number, etc.  
Click Template in the left toolbar, where it will ask if you want to download templates from PufferPanel's GitHub.

![7250be34d9bf2d91f62f9cb86995f7f8](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/7250be34d9bf2d91f62f9cb86995f7f8.webp)

After importing the template, choose `minecraft-vanilla`, which is the official version. Of course, if you have mods you want to install or Bedrock Edition needs, you can choose your own mod loader or `minecraft-bedrock` template.

![7182f5deb2f73a2a199fd00a83189e1e](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/7182f5deb2f73a2a199fd00a83189e1e.webp)

Let's go back to the server section on the left toolbar, add a server by clicking the plus button, and choose the template we imported earlier.

![1c338b8f21107c4a1cb728af5f0d1301](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/1c338b8f21107c4a1cb728af5f0d1301.webp)

The user here is the PufferPanel user that was added at the beginning, this user can manage the server, including using server console, making backup, and changing files.  
This feature is mainly used for multiple administrators, as we only created one user and it has been selected by default, just hit next.

![8d005f319764fd6865e78910ce0380bf](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/8d005f319764fd6865e78910ce0380bf.webp)

This step is all about the detailed settings of our server. If you've run a server before, you should know that these settings are usually in the `server.properties` file, which needs to be set manually before, but now we can just fill them in here.

![50845869b8aeddc1a98b73a9270c8251](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/50845869b8aeddc1a98b73a9270c8251.webp)

- EULA Agreement  
You can directly ask PufferPanel to agree the user agreement.
- IP  
0.0.0.0, as it allow all IPs to connect to the server.
- Java Version  
Fill in the version of Java you installed earlier.
- Memory  
Here is the maximum memory usage, which defaults to 1 GB and will provide 4 simultaneous players. See [here](https://minecraft.wiki/w/Server/Requirements/Dedicated) for the official wiki about memory requirements.  
If you plan to install mods, please increase it as needed.
- MOTD  
Message of the Day, this is the message that appears under the server name. If it is a public server, you can put something like `Maintain by Colgrave`.  
See [here](https://minecraft.wiki/w/Formatting_codes#Use_in_server.properties_and_pack.mcmeta) for the MOTD colors.

![ca1b63c8996ec7e287c19c95ba1de6b6](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/ca1b63c8996ec7e287c19c95ba1de6b6.webp)

- Port  
Server port, fill in the port we set in the firewall.
- Version  
The server version, please note that it must match the Java version.

Click Install in the upper right corner to see the installation is complete and automatically agree to the user agreement.

![aab16b1ebd0ac4d4efe1c95fefc5be76](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/aab16b1ebd0ac4d4efe1c95fefc5be76.webp)

## Editing files and backup solutions
![9f084433556899e4bf3e05979fa6fa91](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/9f084433556899e4bf3e05979fa6fa91.webp)

PufferPanel supports file editing, `server.properties`, `whitelist.json`, `ops.json` can be changed directly from the panel.

![Screencast-3000](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/Screencast-3000.gif)

For backups, you can back up all files directly using the archive button, and you can download it directly from your browser.

### SFTP
PufferPanel also supports SFTP, allowing you to manage server files through software like Filezilla. SFTP server and login information is automatically generated for each server, which makes adding modules much easier.

![732d78d2edb384ea3a08a267be6624ef](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/732d78d2edb384ea3a08a267be6624ef.webp)

Remember to restart the server after changing any files.

## At the end
We went through the basics of setting up a Minecraft server and installing and using PufferPanel, but I can't really write all of it, such as installing mods and running the server with Docker.  
Tinkering is learning, mod installation can be done on your own. I hope this rough guide can help you learn something.

## References
[https://minecraft.wiki/w/Tutorials/Setting_up_a_server](https://minecraft.wiki/w/Tutorials/Setting_up_a_server)  
[https://docs.pufferpanel.com/en/2.x/index.html](https://docs.pufferpanel.com/en/2.x/index.html)  
[https://docs.pufferpanel.com/en/2.x/installing.html](https://docs.pufferpanel.com/en/2.x/installing.html)  
[https://phoenixnap.com/kb/check-java-version-linux](https://phoenixnap.com/kb/check-java-version-linux)  
[https://packages.debian.org/search?keywords=openjdk](https://packages.debian.org/search?keywords=openjdk)
