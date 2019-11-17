---
title: 安装win8.1+kali linux双系统后无引导
date: 2017-05-10 18:10:43
updated: 2017-05-10 18:43:27
categories: 
- 操作系统
tags: 
- Windows
- Linux
- BIOS
---
  
  在装完kali linux时，遇到了一开机就直接进入windows,没有引导，后来才发现，我电脑一开始是通过UEFI安装的win8.1，因为UEFI默认锁定，无法添加引导项，就因为这样，发现重启后没有GRUB菜单，然后去网上找各种教程，都没能解决，像那些使用EasyBCD，EasyEFI之类的软件添加引导时，你会发现，选项那里是灰色的，原因就是因为你目前使用的windows原来可能是UEFI模式下安装的，所以用软件是添加不了的（起码我目前尝试过的方法中不起作用），那现在怎么办，其实我们就是要能够添加到kali linux的启动项就行了。解决办法如下：

*（以下操作以各位的具体机型操作，不过也是大同小异，本人用的是宏碁E5）* 

### 首先进入bios中。
### 找到Security,保证Secure boot mode为Custom,开启这个或许需要设置超级用户密码。     
### 向下找到Select an UEFI file for executing。
### 然后回车进入/EFI/kali/grubx64.efi,选中后，随便输入个名字，记得就行了，搞定后回车会直接跳到Boot页面。
### 会看见有个EFI File Boot 0的选项，将此项移到最前就行了。
### 保存后重启就可以选择windows或者kali linux进入了。    

_其实主要就是在装完linux后要找到引导项就行了，此方法适用在UFEI模式下装的windows，然后装linux双系统的情况下。_
