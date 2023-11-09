---
title: "New theme added + some announcements"
date: 2023-11-08
draft: false
tags: [
"theme","hugo"]
---

Added a new theme to whoisthisjoker.com! Trust me, there is a reason.

So originally I used [hugo.386](https://themes.gohugo.io/themes/hugo.386/) as my theme. It was awesome, and I loved it like crazy. If I had the choice, I would have made that be my permanent theme and I never would have changed it.

for posterity's sake, this is what it looked like:

![old site](/images/oldsite.png)


As awesome as it was, it did NOT play well with pictures. At all. Case in point: My youtube article. One of the extentions has this logo:

![good youtube logo](/images/thumb.jpg)

With the old theme, that same logo looked like this:

![bad youtube logo](/images/bad_color.png)

As you can see, the difference is night and day. 386 was my favorite look for a website EVER...but I cannot deal with the problems related to the images. These are simple examples, but when a picture that was more complex was included it always looked downright unintelligible. 

I decided that, rather than struggling with the javascript of the theme to make the images look good, it would be best to just change the theme wholesale.

Choosing a theme was difficult. I looked at several, but either I couldn't make it work or it was too difficult and messy to edit myself. I chose ink-free because it is relatively easy for me to customize, and add what I need to it. 

## Upcoming stuff

At the moment I am working on an article about customizing the Steam Deck. It is nearly done, but I need to add the images and make sure all the information is correct. 

I love this thing, and since I have been on the road more often than not, I appreciate the opportunity to play Dark Souls in the passenger seat.


## Bibliofile
Also, Bibliofile is nearly complete. I figured out how to go about page turning, scrolling, and bookmarking and in my test cases it worked just fine. However, it is not fully implemented. I just know that it works.

I ditched TUIkit. It had only one example, there was almost no documentation anywhere, and after several months trying to work with it I gave up and switched to Cursive, with Termion as the back end. 

I chose this crate because it not only has LOTS of documentation...like really, a lot...and I can choose several backends. The default backend was ncurses which...yuck. If I have to run Rust in unsafe mode, I might as well use C instead. No point in dealing with the frustrations of Rust if Im just going to use an unsafe library anyway.

Termion had lots of documentation itself in addition to Cursive's documentation.

It looks like a DOS program, which is good because that's what I wanted. 

However, a major reason I started this program was because terminals make excellent dark modes, and I am looking into seeing if I can add color-changing and won't HAVE to stick to blue and grey. However, minimum-viable-product is way more important.

Here is a sneak-peak of the program:

![Bibliofile](/images/bibliofile-sneak-peak.png)

I hope to finish it by end of year, but life comes at you fast and things have gotten a bit wild in my life lately. Almost as much as the beginning of the year was. I am trying to work on it on the weekends and that system seems to be working for me. Needless to say, with how long I have been working on this, I am READY for this project to be completed.

Current TODOs:

 - Finish implementing page turning
 - finish implementing bookmarking
 - add buttons
 - finish library management system
 - add color options

Once it is done:

 - package it for Debian
 - set up download website for the tarball and Windows version(domain bibliofiles.net secured)
 - package it for Arch
 - package it for flatpak

Minimum viable product is nearly complete, but I have a long way to go, even after the programming is done.
