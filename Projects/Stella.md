---
layout: post
title: Stella
date: 2023-07-26
nav_order: 2
parent: Projects
---
# Stella
Stella is a Bash install script for home theater PC.  
It utilizes Arch, KDE Plasma Bigscreen, Kodi and Steam.  

[Link to project](https://codeberg.org/Colgrave/stella)

## How did we get here
I had a Gaming NUC (8i7hnk if you like to know), the attention is to put in the living room for everyone to use.  
Two controllers, running SteamOS, that will be the best little HTPC for me.  

But it didn't satisfy me... (Nothing do)  
I would like to use only the controller to navigate without pulling out my Logitech K400.  

![plasma-bigscreen](https://plasma-bigscreen.org/img/screenshot-1.png)
*Plasma Bigscreen, image copylefted by KDE Community*

I find out [Plasma Bigscreen](https://plasma-bigscreen.org/). It looks great, feels fantastic. While it still in devolpment, I can use it no problem on Arch. And only arch...  
At the moment of writing, Plasma Bigscreen only support on postmarketOS and Manjaro. So this is why I decide using Arch and AUR.  

Would I support other distros?  
Maybe. Let's see after Bigscreen get out beta.  

## How to use it
Simple enough, just run the following command: 
```
bash <(curl -s https://codeberg.org/Colgrave/stella/raw/branch/main/stella.sh)
```

## Future plans
Stella will go through a rewrite at some point.  

I just learned basic of Bash in an afternoon for this project. The code is not great.  

I will move all the Yes and No questions to the front and put the installation processes at the end together. So we don't have to sit there for the next prompt.  

I'll also add full Flatpak support. Retroarch and Steam are kinda broken from the Arch repo.

<script src="https://utteranc.es/client.js"
        repo="C0lgrave34/C0lgrave34.github.io"
        issue-term="pathname"
        label="Comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>