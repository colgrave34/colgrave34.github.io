---
layout: post
title: My Awesome List
date: 2024-04-20
category: post
---
[Awesome Lists](https://github.com/sindresorhus/awesome) are lists of awesome tools, books, guides and media that everyone can contribute to. 

For example: [List of Free Programming Books](https://github.com/EbookFoundation/free-programming-books) and [Awesome Raspberry Pi](https://github.com/thibmaek/awesome-raspberry-pi). 

So I thought, how about I made my own Awesome List. I have a lot of software tools I used every day, privacy focused or just good tools overall, mostly are open source. 

*These are not formal Awesome List* Just so you know.  

&nbsp;
- [Operating Systems](#operating-systems)
  - [Desktop Linux Distros](#desktop-linux-distros)
  - [Server Linux Distros](#server-linux-distros)
  - [Windows](#windows)
- [Networking](#networking)
  - [Router Firmaware](#router-firmaware)
  - [DNS](#dns)
  - [VPN & Proxy](#vpn--proxy)
- [Suring on the Web](#surfing-on-the-web)
  - [Desktop Web Browsers](#desktop-web-browsers)
  - [Mobile Web Browsers](#mobile-web-browser)
  - [Search Engines](#search-engines)
  - [Browser Extensions](#browser-extensions)
- [Communications](#communications)
  - [Real-time Communication](#real-time-communication)
  - [Email](#email)
    - [Email Provider](#email-provider)
    - [Email Client](#email-client)
    - [Email Aliasing Provider](#email-aliasing-provider)
  - [RSS](#rss)
- [Productivity](#productivity)
  - [Office Tools](#office-tools)
  - [Notetaking](#notetaking)
  - [Google Drive Alternatives](#google-drive-alternatives)
- [Creative Tools](#creative-tools)
  - [Image/Digital Drawing](#imagedigital-drawing)
  - [CAD 3D Modeling Tools](#cad--3d-modeling-tools)


&nbsp;
# Operating Systems
## Desktop Linux Distros
Here are desktop distros that I recommend for new users
### [Linux Mint](https://linuxmint.com/)
The "just works" distro.  
If you start your Linux journey, this might be the best distro to try out. 

### [Pop!_OS](https://pop.system76.com/)
It's developed by [System76](https://system76.com/).  
I have used it for at least 2 years, super solid distro.  
Games run perfectly without much tweaking.  
Most of the problem on Ubuntu have fixed here. 

### [Fedora Linux](https://fedoraproject.org/)
My favorite and my daily right now.  
If you want a nearly vanilla distro, Fedora is your choice. 

### [OpenSUSE Tumbleweed](https://get.opensuse.org/tumbleweed/)
OpenSUSE Tumbleweed is a stable rolling release distro with the newest packages. YaST can be really easy for new users. 

## Server Linux Distros
### [Debian](https://www.debian.org/)
You can't go wrong with Debian.  
It's known as the most stable community distro by running old packages. 

### [Rocky Linux](https://rockylinux.org/)
Rocky Linux is an enterprise operating system designed to be compatible with Red Hat Enterprise Linux. 

### [AlmaLinux](https://almalinux.org/)
AlmaLinux is a community owned and governed enterprise Linux distribution.  
It is ABI compatible with Red Hat Enterprise Linux. 

### [OpenSUSE Leap](https://get.opensuse.org/leap/)
OpenSUSE Leap uses source from SUSE Linux Enterprise, which gives an enterprise level of stability to your home lab. 

## Windows
### [SophiApp](https://github.com/Sophia-Community/SophiApp)  
SophiApp is a free, open-source app allows you to delete bloatware, disable telemetry and more. 

[Here](https://wiki.installgentoo.com/images/2/29/Windows10.jpg) is why I prefer Linux.  
But, life isn't perfect. Sometimes we have to use Windows.  
We cannot get rid of every possible problems with Windows, but we can make it better. 

# Networking
## Router Firmaware
### [OpenWrt](https://openwrt.org/)
Put Linux on your old router and make it free and open!  
OpenWrt works better than the stock firmware from their vendor. It offers better stability and more features, such as VPN, DDNS and DNS over HTTPS. 

### [OPNsense](https://opnsense.org/)
OPNsense is an open source, FreeBSD-based firewall and routing software forked from pfSense.  
It has newer packages and faster updates than pfSense. 

### [pfSense](https://www.pfsense.org/)
pfSense is an open source firewall/router computer software based on FreeBSD.  
It has been used by huge corporations and it has provided its stability. 

## DNS
### [Quad9](https://www.quad9.net/)
Non-profit DNS resolver, promise for user privacy and protect user from malware and phishing. 

### [Pi-hole](https://pi-hole.net/)
The self-host option for DNS, provide great ad blocking feature. 

# Surfing on the Web
## Desktop Web Browsers
There are the Web Browsers I tried and used personally.  
For a detailed comparison, please refer to [PrivacyTests.org](https://privacytests.org/).
### ~~[Firefox](https://www.mozilla.org/en-US/firefox/new/)~~
I can't recommend Firefox anymore. Mozilla have been disappointing us again and again, they have approved that revenue is their first priority.  
This is my breaking point as [Firefox now collects user data by default](https://news.ycombinator.com/item?id=40974112).

### [LibreWolf](https://librewolf.net/)
A custom and independent fork of Firefox, with the primary goals of privacy, security and user freedom.  
No telemetry, no tracking. Lots of privacy setting applied by default. Daily right now, highly recommend.

### [Waterfox](https://www.waterfox.net/)
Another fork of Firefox, it's faster, and built without all the telemetry. Tracking protection is enabled by default.  
Is also offers Oblivious DNS as the DNS-over-HTTPS. It also comes with their own themes that look like the classic Firefox.

### [Floorp](https://floorp.app/en)
Floorp is an independent Firefox fork, build by hobbyist Japanese students.  
Beside all the Strong Tracking Protection and No User Tracking, Floorp really shines with its Sidebars, Flexible Toolbar and Tab Bar.  
[Floorp's comparison with Waterfox by their developer](https://github.com/Floorp-Projects/Floorp/issues/100#issuecomment-1272325327)

### [Brave](https://brave.com/)
The zero configuration needed browser with Ad blocker build in.  
Apart from all the Web3 feature, it's a solid browser for someone that don't really want to mess with their browser. 

### [ungoogled-chromium](https://github.com/ungoogled-software/ungoogled-chromium)
Vanilla Chromium but without all Google dependency. 

## Mobile Web Browsers
### [Fennec](https://f-droid.org/packages/org.mozilla.fennec_fdroid/)
Fennec is based on the latest Firefox release (codenamed Fenix).  
It has proprietary bits and telemetry removed, but keep in mind that **it still connects to various Mozilla and Google services that can track users**.

### [Mull](https://f-droid.org/packages/us.spotco.fennec_dos/)
Mull is also based on Fenix.  
But it enables many features upstreamed by the Tor Uplift project, and have every single bit of proprietary bits and telemetry removed. It don't connect to Mozilla and Google services at all.

## Search Engines
### Duckduckgo Lite / HTML
[Duckduckgo Lite](https://lite.duckduckgo.com/lite) and [Duckduckgo HTML](https://html.duckduckgo.com/html) are two non-JavaScript versions of the search engine.  
It's extramly fast and responsive. But it lacks all other features like images, maps etc.

### [Brave Search](https://search.brave.com/)
Independent search engine by Brave Software, Inc. 

### [SearXNG](https://docs.searxng.org/)
Open source, self-hostable, privacy-respecting metasearch engine.  
It uses other search engine's result and combine them together.  
[List of SearXNG instances](https://searx.space/)

## Browser Extensions
### [uBlock Origin](https://ublockorigin.com/)
Free and open-source ad content blocker.  
It doesn't only block ads, also can [bypass paywalls](https://github.com/bpc-clone/bypass-paywalls-clean-filters) and [block YouTube short](https://letsblock.it/filters/youtube-shorts). 

### [Vimium](https://vimium.github.io/)
Use your browser like you use Vim. 

### [Language tools](https://languagetool.org/)
Spelling and grammar checker. 

### [Sponsor blocks](https://sponsor.ajay.app/)
Skip sponsored segments on YouTube and other video platform. 

# Communications
## Real-time Communication
### [Signal](https://www.signal.org/)
Signal is an end-to-end encrypted messaging service.  
They were aiming for beating WhatsApp and fight for user privacy.  
Super user-friendly and only require phone number to sign up.  
Note: *Signal's server is not open source, but the client is.* 

### [Session](https://getsession.org/)
Session is an end-to-end encrypted, decentralized instant messaging application.  
It was originally started as a fork of Signal, but due to concerns about the centralized structure and phone number requirement, they decide to deviate from it.  
Compare to Signal, both all client and server software are open source. It uses a Session code to login, which might be confusion for some users. 

### [Matrix](https://matrix.org/) & [Element](https://element.io/)
Matrix is an open standard real-time communication protocol.  
Besides all the decentralized goodness, it also supports bridges to connect between other chat services, so you can use one app for all your communication needs. 

Element on the other hand is a client application for Matrix, I think it's the best all around app for it. 

## Email
### Email Provider
[Tuta](https://tuta.com/)  
Tuta is an end-to-end encrypted email app and a freemium secure email service based in Germany. 

[Proton Mail](https://proton.me/mail)  
Proton Mail is also an end-to-end encrypted email service founded in 2013 headquartered in Switzerland. 

[Disroot](https://disroot.org/en)  
Disroot project is based in Amsterdam and providing open, decentralized, federated services that respectful freedom and privacy.  
You need to use an email client to use their service. 

### Email Client
[Thunderbird](https://www.thunderbird.net/en-US/)  
Thunderbird is an open source email client from Mozilla.  
After the 115 update, I think everyone should start switching. 

[K-9 Mail](https://k9mail.app/)  
As current maintainer joined to Mozilla Foundation, K-9 Mail plans to be rebranded as Thunderbird for Android. 

### Email Aliasing Provider
[Simplelogin](https://simplelogin.io/)  
Email Aliasing will generate a random, disposable email address for you and forward it to your real email.  
This is useable for one time sign up, trying new services, or just don't want to give out your real email.  
Simplelogin is the only service I tried, it might have better providers out there. 

## RSS
I really don't know where to put RSS...  
### [Thunderbird](https://www.thunderbird.net/en-US/)
Pss... Thunderbird can be used as an RSS reader. 
Truly one App rule them all. 

### [Feeder](https://github.com/spacecowboy/Feeder)
Open source, good-looking Android RSS reader. 

### [Kill the newsletter!](https://kill-the-newsletter.com/)
Do you want to change all the newsletter to RSS?  
There's always some newsletter that don't have RSS support. Kill the newsletter is your bet. 

# Productivity
## Office Tools
### [LibreOffice](https://www.libreoffice.org/)
LibreOffice is a free and open-source office suite from [The Document Foundation](https://www.documentfoundation.org/).  
It was originally forked from OpenOffice. 

### [OnlyOffice](https://www.onlyoffice.com/)
OnlyOffice is an open source office suite.  
If you'd like to switch away from Microsoft Office, OnlyOffice might be the go-to choice. 

## Notetaking
### [Joplin](https://joplinapp.org/)
Joplin is a free and open source note-taking application.  
It supports mutiable synchronisation target such as: Nextcloud, S3, OneDrive, Dropbox or WebDAV. 

### [Simplenote](https://simplenote.com/)
Simplenote is a note-taking application with Markdown support.  
It's for people just want a Markdown supported note-taking App. 

### [SiYuan/思源笔记](https://github.com/siyuan-note/siyuan)
SiYuan is a privacy-first personal knowledge management system.  
SiYuan supports Markdown, notes Graph View and it's self-hostable. 

## Google Drive Alternatives
### [Nextcloud](https://nextcloud.com/)
Nextcloud is an open source suites of software similar to Dropbox, Office 365 and Google Drive.  

# Creative Tools
## Image/Digital Drawing
### [GIMP](https://www.gimp.org/)
GNU Image Manipulation Program is a free and open source graphics editor.  
It is the Photoshop alternative. 

### [Darktable](https://www.darktable.org/)
Darktable is similar to Lightroom, it's an open source photography application and raw developer. 

### [Krita](https://krita.org/en/)
I would like you to stop paying for digital drawing app such as Photoshop, Clip studio and SAI.  
Krita can do everything they can, it's an open source digital art and 2D animation application. 

## CAD & 3D Modeling Tools
### [Blender](https://www.blender.org/)
Blender is an open source 3D modeling tool. 
It has been used in a lot of animation movies and has proven that open source software can be better than Proprietary software. 

### [LibreCAD](https://librecad.org/)
Cross Platform open source 2D CAD software. 

### [FreeCAD](https://www.freecad.org/)
FreeCAD is an open source 3D CAD software. 

### [KiCad](https://www.kicad.org/)
The PCB designing CAD software.  
Most of the open source PCB are designed by using KiCad. 
