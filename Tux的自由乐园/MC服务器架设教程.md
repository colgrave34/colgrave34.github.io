---
layout: default
title: MC服务器架设教程
nav_order: 1
parent: Tux的自由乐园
---
这是服务器端架设方法，万一以后没人管了还有救.  
我是用[debian](https://www.debian.org/)，稳定简单.  
其他发行版都可以安装，但请自行谷歌。

# 安装
ssh远程控制

## 2. 服务器用户
### 添加服务器用户
不要用root用户跑命令！稍微一错全完蛋。所以新建一个用户出来，给root权限就好。
```
adduser colgrave
```
### 更改用户权限
把用户 `colgrave` 加入 `sudo` 组
```
usermod -aG sudo colgrave
```
退出root用户
```
exit
```
用新用户登录
```
ssh colgrave@192.186.0.0
```
## 3. 禁用root通过ssh登录
为了增强安全性，禁用`root`通过`ssh`登录
```
sudo nano /etc/ssh/sshd_config
```
重启`ssh`
```
sudo service sshd restart
```
## 4. 系统更新
```
sudo apt update && sudo apt upgrade -y
```
## 5. 设置自动更新
```
sudo apt install unattended-upgrades #安装自动更新
sudo nano /etc/apt/apt.conf.d/50unattended-upgrades #设置自动更新
```
检查
```
apt-config dump APT::Periodic::Unattended-Upgrade
```
## 6. 安装
我们需要安装`Java17`和`Pufferpanel`。[Pufferpanel](https://www.pufferpanel.com/)是一个网页UI服务器管理。  
电脑白痴类型管理，安就完事了。  
[如果不知道下哪个Java](https://packages.debian.org/search?keywords=openjdk)，其他发行版自行谷歌。
```
curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh | sudo bash
sudo apt update
sudo apt install openjdk-17-jre-headless pufferpanel -y #安装Java和Pufferpanel
sudo apt autoremove #删除多余安装包
```
## 7. 防火墙设置
```
sudo ufw allow ssh
sudo ufw allow 8080/tcp #Pufferpanel端口
sudo ufw allow 25565/tcp #Minecraft服务器端口
sudo ufw enable #启用ufw防火墙
sudo ufw reload #重启ufw防火墙
```
## 8. 添加Pufferpanel用户
```
sudo pufferpanel user add
```
## 9. 设置开机自启动
```
sudo systemctl enable --now pufferpanel
```

# 安装后
## Pufferpanel设置
## online-mode
如果大家没有正版，在用HMCL启动器，关闭`Server.properties`文件里的`online-mode`
```
online-mode false
```

# 域名设置
## Caddy
### 安装Caddy
```
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt install caddy
sudo apt autoremove
```
### 设置开机自启动
```
sudo systemctl enable --now caddy
```
### 防火墙设置
```
sudo ufw allow https #打开https端口
sudo ufw deny 8080/tcp #关闭Pufferpanel端口
sudo ufw reload #重启ufw防火墙
```
