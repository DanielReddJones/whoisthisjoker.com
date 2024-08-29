---
title: "Using Slackware for one year"
date: 2025-08-28
draft: true
tags: [
  "Linux", "Unix", "Slackware", "Journal"]
categories: [
  "Linux", "personal", "reviews"]
---

# I Used Slackware For One Year And This Is How It Went:

[![Slackware Tux](/images/slackware_journal/SWtuxgnu.png)](http://www.slackware.com/)

## Introduction

This is a secret article that I will publish on August 27th, 2025. I will use Slackware 15.0 for one year, and document how things run on it and what it was like. I decided to do this challenge because with how many distros there are and how far removed Linux has gotten from the Unix Philosophy(it never adhered to that strictly to begin with, but I digress) I felt that it would be a fun challenge to use the oldest currently maintained distro for one year, and see what it is like.

Full disclosure, I DID use Slackware before, but only had it for one day before deciding it was too inconvenient and installed POP_OS. So besides running it for like, five minutes, I am a total N00B to Slackware.

I will update this at least once a week until I reach the one-year mark, which is when I will set this article from draft to publish. I will also create an article for installing Slackware for UEFI devices, which you can find [here](). There are tons of articles for installing it, but surprisingly few for installing on modern hardware. Every tutorial seems to assume that you are running it in a VM which requires a BIOS installation instead of UEFI, so that article should help SOMEBODY in desperate need.

This article is also a project to help me stop distro-hopping. It has gotten to the point where I change distros once every three months out of boredom, but it has become a habit rather than a real desire to switch.

Lastly, I hope this helps somebody in making the decision to switch to Slackware. I was on the fence about using it again despite the fact that a lot of it appeals to my sensibilities(inconveniences aside) and there aren't any reviews for Slackware from someone that uses it as a daily driver. If you are reading, I hope that this helps you in your decision!

![think slack](/images/slackware_journal/thinkslack.png)

## August 28, 2024

As of last night, I have installed Slackware 15 onto my laptop. The setup process was a bit more complicated than I remembered. Every article and video I found for installing Slackware required me to install GRUB separately for UEFI, or was a tutorial for BIOS devices.

To get it installed I created three partitions: 

 - A root partition
 - A Swap partition
 - An EFI partition

I then went through the normal install process, but then chose ELILO instead of LILO, and had it choose my EFI partition as the boot partition.

Another frustrating bit is that, if you do not install GRUB, ELILO only wants to pick up on the root directory instead of the home directory. I had an issue with that so I wiped my drive and made my home and root directories one and the same so I wouldn't have to go through the bother of installing, configuring, and running GRUB since it does not come preinstalled. 

I then created my user, dan, and assigned sudo permissions. For my window manager, I went with FVWM2 for its configurability. Slackware does not come with FVWM3 to my frustration, but I may switch to something else entirely in a while. Been looking at Hyprland since it is pretty neat looking, or to something else depending on my needs.

As for software packages, I installed every package group except for the KDE and XFCE package groups. It didn't make sense to install it since I intend on only using window managers.

I ran out of time last night and had to go to bed, but later today I am planning on installing [SpaceFM](https://ignorantguru.github.io/spacefm/) as my default file manager. It's stupidly configurable, so it seems like a good option for me. This week will probably have the most articles of any other week since I am still getting it configured to my liking.

I also pay for Jetbrains tools because I like their IDEs, so I am going to need to get that up and runnning on Slackware as well. Will update with screenshots later.

## August 29, 2024

I decided to install i3 and set it as my default window manager. It is the window manager that I am most familiar with, and in taking on a new system where everything is alien I decided to go with what is most comfortable to me. 

I learned that, if a package isn't in Slackpkg, you have to either compile it yourself or install it via slackbuilds. Slackbuilds is pretty simple, but it is annoying when there are dependencies because I have to install that too. The way it works is that you download the slackbuild file, unzip it, then put the archive folder of the source code you want to build in the folder with your slackbuild file. Then you run packagenamehere.Slackbuild and it creates a file in your /tmp folder that you can install with the program installpkg. 

It is easier on other distros to be sure. This is not the standard Linux experience in 2024. It IS the standard Linux experience of the 1990s from what I hear. 

To streamline this process, I found a package manager that automatically compiles slackbuild packages called sbopkg. It automates the whole process for you and gets rid of the tedious steps. I think that and Flatpak are going to be my main two package managers for this challenge. Sbopkg supposedly has a way to automatically install dependencies from what I read but I have not figured that out yet.

Now that I figured out a simple way to get packages installed, I am going to figure out how to get flatpak installed tonight so that I can install proprietary apps such as Steam for when I, well, want to blow off some steam. I also need to get some customization programs for i3 installed such as i3-gaps, feh, and others. I also ran into an issue where spacefm does not want to see any files in any folders. I am unsure why that is the case, but a little searching might help me figure out why this is the case.