---
layout: post
title: PufferPanel 让你的 MC 服务器变简单
date: 2024-06-23
category: linux灯塔
---
![eb7e4f405901458e80a9569d6bd8f6fa](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/eb7e4f405901458e80a9569d6bd8f6fa.webp)  

记得几个月前，几个朋友忽然想玩 Minecraft（也是打游戏的时候突然提到）。找了好几家服务器代理，价格都不太合适。  

发几张图大家感受一下。

Minecraft Realms 是 MC 官方的服务器租赁，Java 版本每个月要 7.99 刀。。。

![18fb94a49b3e44609e637e4eb4775c43](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/18fb94a49b3e44609e637e4eb4775c43.webp)

Bisect 和 Apex 都是打广告相当凶的两个公司，4 GB 内存的租赁也在 10 刀左右。

![d20069d061cc445dbbc2a0b88bc75979](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/d20069d061cc445dbbc2a0b88bc75979.webp)

![d859259deebd43c8972248041f73b68c](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/d859259deebd43c8972248041f73b68c.webp)

对于几个学生党，零花钱将将好够吃饭，租个服务器可能也就玩个两三个月，相当没必要。
> 我记得网易也有官方的服务器来着，找了半天没找到。  
> 也是因为价格太高被我们否了。

最后想着算了，找台旧电脑自己跑服务器吧，内存还比 4 GB 多。

在花时间找网页管理的时候忽然找到个好玩意。[PufferPanel](https://www.pufferpanel.com/) 是一个开源的网页游戏服务器管理。在我试过的众多我的世界游戏服务器里，操作最简单，最易用的了。不仅支持我的世界，像 ARK，GMod，Palworld，Terraria，Zomboid 都支持。  
游戏支持列表：[https://github.com/pufferpanel/templates](https://github.com/pufferpanel/templates)

![200de389e976f65034db0fdf2c2d96f2](https://docs.pufferpanel.com/en/2.x/_images/serverlist.png)
图片来源：[https://docs.pufferpanel.com/en/2.x/featuretour.html](https://docs.pufferpanel.com/en/2.x/featuretour.html)
> 傻瓜式服务器部署，安就完事了。

此指南以 Linux 为系统，[Debian](https://www.debian.org/) 为发行版，并且跳过所有服务器准备工作（SSH登录设置，添加服务器用户，系统更新以及自动更新）。  
其他发行版也可以像理论上一样安装，但某些步骤会有所不同。

## Java
咱们首先确定 Java 版本，根据 Mincraft 服务器的版本，Java 的版本也会有所不同。

|服务器版本|所需 Java 版本|
|-|-|
|Minecraft 1.17|JRE 16 或更高版本|
|Minecraft 1.18|JRE 17 或更高版本|
|Minecraft 1.20.5 或更新版本|JRE 21 或更高版本|

> 虽然服务器可以在旧版本的 Java 上运行，但新版本会提供错误修复、更高的稳定性、安全性和性能。

应用自[官方 Wiki](https://minecraft.wiki/w/Server/Requirements#server_requirements)

### JRE 和 JDK 的区别
大家在软件库里面搜索安装的时候会发现有 4 个包。

![25a0c50b7121dc2163cbea9d8280c56b](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/25a0c50b7121dc2163cbea9d8280c56b.webp)

JRE 是指 Java Runtime Environment，是为运行 Java 程序而设计的软件包工具。而 JDK 是为开发 Java 程序而设计的工具包。  
Headless 是指不需要图形界面支持的版本。  
跑服务器只需要 `jre-headless` 就可以了，当然你要是有 JDK 也不需要卸载，JDK 包括了 JRE 。

### 如何查看 Java 版本
在命令行里输入：
```bash
java -version
```
这样可以确认你的安装版本。

![31cbe63874f3c05c317d18ad77e1b117](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/31cbe63874f3c05c317d18ad77e1b117.webp)

## 安装
安装教程以 Java 17 为例。
```bash
# 添加 PufferPanel 添加仓库
curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh | sudo bash
# 更新软件库
sudo apt update
# 安装 Java 17 和 PufferPanel
sudo apt install openjdk-17-jre-headless pufferpanel -y 
```

### 防火墙设置
```bash
# 允许 Pufferpanel 网页端口连接
sudo ufw allow 8080/tcp
# 允许 Minecraft 服务器端口连接
sudo ufw allow 25565/tcp
# 启用 ufw 防火墙
sudo ufw enable
# 重启 ufw 防火墙
sudo ufw reload
```

### 添加 PufferPanel 用户
```bash
sudo pufferpanel user add
```

![27350f155c147ed13bc505072f4f24bf](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/27350f155c147ed13bc505072f4f24bf.webp)

PufferPanel 会让你确认用户信息，并问你是否是管理员。  
Email 这里主要用于登陆，也可以用于[通知功能](https://docs.pufferpanel.com/en/stable/guides/email.html)，这需要用 SMTP 连接到一个邮箱，我个人没有试过，也不好多说。

### 设置开机自启动
```bash
sudo systemctl enable --now pufferpanel
```
如果一切顺利的话，打开浏览器输入 `http://<服务器ip>:8080` 就可看到 PufferPanel 了。

![a7af0390b865390544f1337aeb4920ca](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/a7af0390b865390544f1337aeb4920ca.webp)

## 服务器安装设置
PufferPanel 是以模板（Template）的形式来设置以及启动服务器，模板里包括了服务器名称，端口设置等等。  
在左边工具栏里点击 Template，这里会询问是否从 PufferPanel 的 GitHub 上下载模板。

![7250be34d9bf2d91f62f9cb86995f7f8](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/7250be34d9bf2d91f62f9cb86995f7f8.webp)

点击确认后就可以导入模板了，这里选择 `minecraft-vanilla`，也就是官方版本。当然如果有 mod 或者 Bedrock 的需求话，可以选择自己的 mod loader 或者 `minecraft-bedrock` 模板。

![7182f5deb2f73a2a199fd00a83189e1e](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/7182f5deb2f73a2a199fd00a83189e1e.webp)

咱们回到左边工具栏的 Server 选项，右下角加号添加服务器。选择刚才添加的模板。

![1c338b8f21107c4a1cb728af5f0d1301](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/1c338b8f21107c4a1cb728af5f0d1301.webp)

这里的用户是指一开始添加的 PufferPanel 用户，这个用户可以管理服务器，包括服务器指令，备份以及更改文件。  
这个功能主要用于多个管理员，因为刚才我们只创建了一个用户，而且已被默认选用，这里点下一步就好。

![8d005f319764fd6865e78910ce0380bf](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/8d005f319764fd6865e78910ce0380bf.webp)

这一步就是我们服务器的详细设置了。跑过服务器的小伙伴应该都知道，这些详细设置一般都是在服务器属性的明文文件（server.properties）里，原来我们都需要手动设置，现在直接填进去就好。

![50845869b8aeddc1a98b73a9270c8251](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/50845869b8aeddc1a98b73a9270c8251.webp)

- EULA Aggrement  
这里可以直接让 PufferPanel 同意用户协议。
- IP  
IP 这里填 0.0.0.0 就好，让服务器接受所有 IP。
- Java Version  
Java 版本，这里填写一开始下载的 Java 版本。
- Memory  
这里是最大内存使用量，默认是 1 GB，大概可以提供 4 人同时连接。官方 Wiki 内存需求请看[这里](https://minecraft.wiki/w/Server/Requirements/Dedicated)  
如果有装 mod 的话请根据所需提高。
- MOTD  
Message of the Day，这是显示在服务器列表中，服务器名称下面的的信息。如果是公开服务器的话，可以填写像 `Maintain by Colgrave` 的字样。  
MOTD 颜色字样请看[这里](https://minecraft.wiki/w/Formatting_codes#Use_in_server.properties_and_pack.mcmeta)。

![ca1b63c8996ec7e287c19c95ba1de6b6](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/ca1b63c8996ec7e287c19c95ba1de6b6.webp)

- Port  
服务器端口，这里填写我们之前在防火墙设置的端口。
- Version  
服务器版本，这里注意一定要与 Java 版本符合。

点击右上角的安装，就可以看到 Console 里面的安装并同意了用户协议。

![aab16b1ebd0ac4d4efe1c95fefc5be76](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/aab16b1ebd0ac4d4efe1c95fefc5be76.webp)

## 文件编辑以及备份
![9f084433556899e4bf3e05979fa6fa91](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/9f084433556899e4bf3e05979fa6fa91.webp)

PufferPanel 支持文件编辑，像 `server.properties`，`whitelist.json`，`ops.json` 都可以直接在面板上更改。

![Screencast-3000](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/Screencast-3000.gif)

备份而言，在文件管理的右上角可以直接备份所有文件，直接可以从浏览器下载。

### SFTP
PufferPanel 同时支持 SFTP，通过像 Filezilla 的软件可以直接管理服务器文件。每个服务器会自动生成 SFTP 服务器和登陆信息，这可以让添加模组简单许多。

![732d78d2edb384ea3a08a267be6624ef](/assets/img/2024-06-23-pufferpanel-makes-your-mc-journey-easier/732d78d2edb384ea3a08a267be6624ef.webp)

更改完任何文件记得重启服务器。

## 写在最后
这篇文章主要讲了一下 Minecraft 服务器的基础设置，以及安装使用 PufferPanel。其他的实在写不进去了，像 mod 的安装以及以 Docker 运行服务器都没有包含进去，见谅。  
折腾及学习，像 mod 安装可以自己琢磨一下。希望这篇粗略的指南能让大家学到点东西。

## 参考
[https://minecraft.wiki/w/Tutorials/Setting_up_a_server](https://minecraft.wiki/w/Tutorials/Setting_up_a_server)  
[https://docs.pufferpanel.com/en/2.x/index.html](https://docs.pufferpanel.com/en/2.x/index.html)  
[https://docs.pufferpanel.com/en/2.x/installing.html](https://docs.pufferpanel.com/en/2.x/installing.html)  
[https://phoenixnap.com/kb/check-java-version-linux](https://phoenixnap.com/kb/check-java-version-linux)  
[https://packages.debian.org/search?keywords=openjdk](https://packages.debian.org/search?keywords=openjdk)
