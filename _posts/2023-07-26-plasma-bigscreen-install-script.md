---
layout: post
title: Plasma Bigscreen Install Script
date: 2023-07-26
category: projects
---
A Plasma Bigscreen install script for Arch Linux. 

[Project Link](https://codeberg.org/Colgrave/plasma-bigscreen-install-script){: .btn .btn-outline }

## How did we get here
I had a Gaming NUC (8i7hnk if you like to know), the attention is to put in the living room for everyone to use.  
Two controllers, running SteamOS, that will be the best little HTPC for me.  

But it didn't satisfy me... (Nothing do)  
I would like to use only the controller to navigate without pulling out my Logitech K400.  

![plasma-bigscreen](https://plasma-bigscreen.org/img/screenshot-1.png)
*Plasma Bigscreen, image copyright by KDE Community*

I find out [Plasma Bigscreen](https://plasma-bigscreen.org/). It looks great, feels fantastic. While it still in devolpment, I can use it no problem on Arch. And only Arch...  
At the moment of writing, Plasma Bigscreen only support on postmarketOS and Manjaro. So this is why I decide using Arch and AUR.  

Would I support other distros?  
Maybe. Let's see after Bigscreen get out beta.  

## How to use it
Simple enough, just run the following command: 
```
bash <(curl -s https://codeberg.org/Colgrave/plasma-bigscreen-install-script/raw/branch/main/pbinstall.sh)
```