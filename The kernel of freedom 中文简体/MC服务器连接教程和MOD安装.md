---
layout: default
title: MC服务器连接教程和MOD安装
nav_order: 2
parent: The kernel of freedom 中文简体
---
# MC服务器连接教程和MOD安装
写的不全，见谅！  
~~[云盘提取链接]()~~  
云盘下载作废，请群文件下载

## 1. Java
安装Java
我在包里放了一个Java17稳定版，直接安装就行![Screenshot from 2022-07-29 14-22-22](https://user-images.githubusercontent.com/31970387/181821333-d1f7e2a7-0855-4088-82b1-9ea4e2fe0bf9.png)

也可以直接去[Oracle官网](https://www.oracle.com/java/technologies/downloads/#java17)下载
`x64 Installer`和`x64 MSI Installer`都可以  

## 2. Hello Minecraft! Launcher
安装HMCL启动器  
包里有，直接运行  
网速好的同学可以直接去官方[Github](https://github.com/huanghongxun/HMCL)下载，[官网](https://hmcl.huangyuhui.net/)下载打不开... 

## 3. 运行及安装游戏
打开HMCL大概是这个样子的
![Screenshot 2022-07-29 121918](https://user-images.githubusercontent.com/31970387/181821626-258e647b-81ae-4edc-8d78-1e578651ccf7.png)
点击左侧`没有游戏版本`去下载游戏

**现阶段为了兼容性和稳定性，服务器游戏版本是`1.18.2`，Forge版本`40.1.59`**

选择游戏版本`1.18.2`，Forge选择安装`40.1.59`  
其他都不要安装
![Screenshot 2022-07-29 122014](https://user-images.githubusercontent.com/31970387/181821829-c2496f52-5bb3-4e3c-9306-a0fe70321ca3.png)
安装界面：
![Screenshot 2022-07-29 122043](https://user-images.githubusercontent.com/31970387/181821726-3e85900c-f0d5-43d8-a42b-a8842bc7873b.png)

## 4. 安装MOD
游戏安装完成，现在回到主界面，点击左手边`游戏 ---> 1.18.2 ---> 模组管理 ---> 添加模组`
![Screenshot 2022-07-29 122124](https://user-images.githubusercontent.com/31970387/181821893-5f9d44fc-7892-41fe-99d3-305581801d23.png)
把包里的MOD全部塞进来就行：
![Screenshot 2022-07-29 122134](https://user-images.githubusercontent.com/31970387/181825525-9461b4c5-5c02-4a53-87ad-cf75cee911e9.png)
成功添加MOD：
![Screenshot 2022-07-29 122142](https://user-images.githubusercontent.com/31970387/181821944-4c9bb444-1b42-4a7a-a68a-e1cff45edb2c.png)
这里有三个选装MOD：  
[Rubidium](https://www.curseforge.com/minecraft/mc-mods/rubidium) 提高性能，增加帧数  
[Oculus](https://www.curseforge.com/minecraft/mc-mods/oculus) 光影必装  
[BSL Shaders](https://www.curseforge.com/minecraft/customization/bsl-shaders) 光影包  
可装可不装，看自己情况  
光影指南在[这里](https://colgrave34.github.io/%E4%B8%AD%E6%96%87%E6%8C%87%E5%8C%97/%E5%A5%BD%E5%85%84%E5%BC%9F%E4%BB%AC%E7%9A%84mc%E6%9C%8D%E5%8A%A1%E5%99%A8/#%E5%85%89%E5%BD%B1%E5%AE%89%E8%A3%85)

**其他MOD请勿安装，会与服务器冲突**

## 5. LINK START! 
### 用户名
进服务器之前记得改用户名
![Screenshot 2022-07-29 143825](https://user-images.githubusercontent.com/31970387/181826050-5a35a735-6223-4670-9d11-bc2478e2d001.png)
### 启动游戏
可以启动游戏了，右下角直接 LINK START!  
![Screenshot 2022-07-29 122159](https://user-images.githubusercontent.com/31970387/181822196-08042e47-9afd-4879-9330-0e7fddcf3d73.png)
### 查看MOD
进入MC主界面后，可以检测一下MOD安装是否成功。左下点击`Mod`
![Screenshot 2022-07-29 122230](https://user-images.githubusercontent.com/31970387/181822218-0bb07919-0dc7-40e1-9865-a612971bd004.png)
### 加入服务器
点击`多人游戏 ---> 添加服务器`
![Screenshot 2022-07-29 122240](https://user-images.githubusercontent.com/31970387/181822241-a1742182-4304-44d9-878e-16f50c3f8c16.png)
服务器名称随意填就好了，服务器地址是服务器IP，不知道的去群里要

# 常见问题

**MOD更新请通知我**

## 游戏打不开看这里
### Java
**老版Java记得卸载**  
保留老版可能会有冲突  
卸载老版安装新版，记得重启

### Optifine
**服务器不支持 Optifine (暮色森林MOD不支持)**
Optifine 可以 Rubidium 和 Oculus 代替，两个加起来效果是和 Optifine 一样的

## MOD指南
### Inventory Sorter (一键整理)
鼠标中键整理，滚轮滚动依次放入拿出1个单位

### 小地图设置
![image](https://user-images.githubusercontent.com/31970387/182047079-1d2ff9e0-3aee-49c4-aae4-00fb566e7203.png)
#### 更改小地图形状
回到`主界面 ---> Mods --->`  
找到左边列表里的 `Xaero's Minimap ---> Config ---> View ---> Settings ---> Shape`
#### 小地图锁定向北
`主界面 ---> Mods ---> Xaero's Minimap ---> Config ---> View ---> Settings ---> Lock Minimap North`

### 光影安装
以MOD模式安装 `Rubidium` 和 `Oculus`
![Screenshot 2022-07-31 175242](https://user-images.githubusercontent.com/31970387/182047053-640f832d-c6b2-4bc7-ab84-45ab2a2e83c7.png)
进入游戏后， `设置 ---> 视频设置 ---> 光影包` 之后拖进来就行了
![Screenshot 2022-07-31 175546](https://user-images.githubusercontent.com/31970387/182047058-dbf821a8-2312-43a2-a6c5-59080f4942b6.png)

### 皮肤
皮肤需要在启动器中设置
![Screenshot 2022-07-29 122302](https://user-images.githubusercontent.com/31970387/181822270-b5f190d4-e5af-4284-a5e8-76d9dd98dac9.png)
左边`账户 ---> 右边的小衣架`
![Screenshot 2022-07-29 122310](https://user-images.githubusercontent.com/31970387/181822297-062c905b-eafa-42f5-bb66-826304308457.png)

# MOD列表
1. [MrCrayfish's Furniture Mod](https://www.curseforge.com/minecraft/mc-mods/mrcrayfish-furniture-mod)
2. [Corpse](https://www.curseforge.com/minecraft/mc-mods/corpse)
3. [Dynamic Lights](https://www.curseforge.com/minecraft/mc-mods/dynamic-lights)
4. [FallingTree](https://www.curseforge.com/minecraft/mc-mods/falling-tree)
5. [Inventory Sorter](https://www.curseforge.com/minecraft/mc-mods/inventory-sorter)
6. [Just Enough Items (JEI)](https://www.curseforge.com/minecraft/mc-mods/jei)
7. [Open Parties and Claims](https://www.curseforge.com/minecraft/mc-mods/open-parties-and-claims) ---> 正式服添加
8. [Traveler's Backpack](https://www.curseforge.com/minecraft/mc-mods/travelers-backpack)
9. [The Twilight Forest](https://www.curseforge.com/minecraft/mc-mods/the-twilight-forest)
10. [Xaero's World Map](https://chocolateminecraft.com/worldmap.php)
11. [Xaero's Minimap](https://chocolateminecraft.com/minimap2.php) ---> 正式服更改为[FAIR-PLAY VERSION](https://chocolateminecraft.com/minimap2.php)

## 选装
1. [Rubidium](https://www.curseforge.com/minecraft/mc-mods/rubidium)
2. [Oculus](https://www.curseforge.com/minecraft/mc-mods/oculus)
3. [BSL Shaders](https://www.curseforge.com/minecraft/customization/bsl-shaders)


*07/31/2022 更新  服务器版本 beta-0.2.2*