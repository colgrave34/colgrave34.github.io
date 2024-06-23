---
layout: post
title: The Death of CentOS
date: 2024-06-09
---
![cd4d555944999958b29f9619f5ef99a0](/assets/img/2024-06-09-the-death-of-centos/cd4d555944999958b29f9619f5ef99a0.webp)

CentOS 7 is going to end its update next mouth, with this opportunity I'd like to talk about the history of Red Hat, CentOS, and what the hell happened in the past two years.

# Red Hat and Its Distros
## Red Hat Enterprise Linux
In October 1994, Marc Ewing, who was working at IBM, built his first Linux distro.  
At the same year, ACC Corporation who saw a good opportunity, bought out his distro, merged the sales and software development. Red Hat Enterprise Linux was born.

## CentOS
CentOS, Community Enterprise Operating System, was build by Gregory Kurtzer in 2002 as a community distro.

CentOS is a downstream fork of Red Hat. It's like the relationship between Debian and Ubuntu, of course with Ubuntu has more up-to-date software. RHEL and CentOS is basically the same, beside all the logos. All the updates going from RHEL to CentOS. With this kind of stability, CentOS soon attract a lot of love from hobbyist and small companies. This is the main reason why CentOS become this most popular server distro in 2010.

In 2014, Red Hat decided to sponsor CentOS with the condition that all the trademarks and ownership must be transferred to Red Hat. This was a good thing for CentOS, which was only supported by the community donations.

## Fedora
Fedora, on the other hand, is a desktop focused distro which is a project under Red Hat, and an upstream for RHEL.  
So Fedora has the most up-to-date software, also act as a testing distro.  
RHEL as a downstream distro, accepting the software already tested on Fedora, providing server graded stability. CentOS copy and modify RHEL's source code.

## Cost
As an enterprise focused distro, RHEL's cost is similar to Ubuntu server, there's not much cost for personal uses, but it will be costly if it was in a business environment.  
CentOS, as a community distro, does not charge for its use, which is why it is so popular with hobbyists and small companies.

# So What Happened
## The Death of CentOS and the Birth of Stream
IBM acquired Red Hat for $34 billion in 2018, and Red Hat has been under IBM's umbrella as an independent subsidiary.  
With all the ownership of CentOS, Red Hat unilaterally terminated CentOS's development at the end of 2020, and require full commitment to CentOS Stream development by the end of 2021.

Of course, in order to turn a profit, Red Hat turned CentOS Stream into a midstream, the downstream of Fedora and upstream of RHEL. At the same time, CentOS Stream became unstable.

Red Hat's intentions are clearly obvious, CentOS not only bring RHEL level's stability, but also freely available to the public. This move is to push companies to buy Red Hat's service and prevent using CentOS. I don't have to tell you how upset people are. Individual users of course, the worst scenario is reinstalled system, change to a different distro. But small companies who have been using CentOS for years now only have two choices, change all system to a not so stable CentOS Stream, or spend a lot of money to pay up Red Hat.

# Alma and Rocky's Resist
Lucky enough, open source is still open source. Alma and Rocky announce to make distros that's 1:1 compactible with RHEL.

AlmaLinx was announced by CloudLinux, with the hope AlmaLinux continue CentOS's spiritual goal. On March 30, 2021, AlmaLinux OS Foundation took over the development and management from CloudLinux to become a fully community based distribution, with CloudLinux committing $1 million per year to fund the project.

Rocky on the other hand was created by Gregory Kurtzer, one of the original founders of CentOS, with the same goal of compatible with RHEL. The name was to pay homage to Rocky McGaugh, an early co-founder of CentOS.  
Beside the 1:1 compatibility, Alma and Rocky also provide easy-to-use migration scripts. With this, the soul of CentOS stayed with us for another two years.

## Red Hat's Paywall and GPLv2
In June of last year, Red Hat stop making the RHEL source available to the public. The source code is still available to Red Hat's paid consumer, but with the new condition that redistribution is prohibited. 
> Isn't RHEL using GPLv2 license?

Yes, but Red Hat found some gray area in the license.  
Let's talk about GPLv2 license, it does mention you must make the source code available if you make executables available to your users. But it doesn't mean you HAVE TO make the source code available to the world, in which case Red Hat has a reason to only make it available to paying customers.

At the same time, GPLv2 doesn't say anything about additional agreement, so they grab the opportunity and add a EULA.  
Excerpt from [RHEL EULA](https://www.redhat.com/licenses/Appendix_1_Global_English_20230309.pdf#page=4):
> (g) Unauthorized Use of Subscription Services. Any unauthorized use of the Subscription Services is a material breach of the Agreement. Unauthorized use of the Subscription Services includes:… (d) using Subscription Services in connection with any redistribution of software…

Such user agreement is paradoxical with GPLv2.  
Excerpt from [GPLv2](https://opensource.org/license/gpl-2-0/):
> Each time you redistribute the Program (or any work based on the Program), the recipient automatically receives a license from the original licensor to copy, distribute or modify the Program subject to these terms and conditions. You may not impose any further restrictions on the recipients exercise of the rights granted herein.

Greedy Red Hat has even gone so far as to publicly state that if you need the source code, you should refer to the CentOS Stream.  
Without upstream's source code, downstream distro of course having a bad time updating. Not only Alma and Rocky, but also Oracle and SUSE, are effected.

Whether or not Red Hat is violating the license is still in debate, it's quite unrealistic to get a response at this stage.

## Where does Alma and Rocky go from here?
![3daba14bef8d4608bd4922f2a5402905.png](/assets/img/2024-06-09-the-death-of-centos/3daba14bef8d4608bd4922f2a5402905.webp)

In August 2023, CIQ (the company behind Rocky), Oracle, and SUSE joined forces to create OpenELA, not only in protest, but also as a way to work together to ensure the 1:1 compatible with RHEL. The main task was to pick and fix software from the CentOS Stream to achieve the goal.

Alma, on the other hand, has chosen to become a fork of RHEL and is not aiming for a 1:1 compatible anymore. But supported on the OpenELA project.

## For hobbyist
> Jeff Geerling: A few years ago, I would've said CentOS or Debian. Now, the answer is much easier.

![ee0c73f4a12a462ab495d5aace3616dd.png](/assets/img/2024-06-09-the-death-of-centos/ee0c73f4a12a462ab495d5aace3616dd.webp)

# Reference
[https://en.wikipedia.org/wiki/Red_Hat_Enterprise_Linux](https://en.wikipedia.org/wiki/Red_Hat_Enterprise_Linux)  
[https://en.wikipedia.org/wiki/CentOS](https://en.wikipedia.org/wiki/CentOS)  
[https://en.wikipedia.org/wiki/AlmaLinux](https://en.wikipedia.org/wiki/AlmaLinux)  
[https://en.wikipedia.org/wiki/Rocky_Linux](https://en.wikipedia.org/wiki/Rocky_Linux)  
[https://opencoreventures.com/blog/2023-08-redhat-gets-around-gplv2-license-intention-with-contract-law/](https://opencoreventures.com/blog/2023-08-redhat-gets-around-gplv2-license-intention-with-contract-law/)  
[https://www.jeffgeerling.com/blog/2023/gplv2-red-hat-and-you](https://www.jeffgeerling.com/blog/2023/gplv2-red-hat-and-you)  
[https://www.redhat.com/licenses/Appendix_1_Global_English_20230309.pdf#page=4](https://www.redhat.com/licenses/Appendix_1_Global_English_20230309.pdf#page=4)  
[https://opensource.org/license/gpl-2-0/](https://opensource.org/license/gpl-2-0/)
