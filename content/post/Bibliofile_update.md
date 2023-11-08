---
title: "Bibliofile update"
date: 2023-07-24T21:59:10-05:00
draft: false
tags: [
  "Programming", "self_hosting", "Microsoft", "Github"]
categories: [
  "Programming"]
---

## Bibliofile_update
v. 1.0 did not release over July 4th break, and I did not update with a new post. Shame on me. 
It is very hard to self-motivate on personal projects, especially when you have family coming over, and you are getting ready to celebrate something. I don't really have a good excuse...and because this project is solely for me, I am the one that I have failed. 

Anyway, I started work on it again. Having never used a TUI framework before, it took me a bit to figure out TUIKit. I kept trying to get a hello world setup working with it and I finally figured it out, as TUIKit does not have much documentation outside the crates.io page. The weird thing about the crates.io page for TUIKit is that it shows how to move text around on the TUI, but not simply display text. 

Both use different methods to accomplish the goal, so it is very weird to me that they decided to showcase something more advanced instead of showing off the basics first. Even ChatGPT spat out nonsense when I asked how to make a hello world program for the framework.


To make a basic "Hello World" program in TUIKit, first you of course have to import parts of the library:

```rust
use tuikit::term::{Term, TermHeight};
use tuikit::prelude::*;
```

Then you have to write out the following code in your function:

```rust
fn my_func() {
    let term: Term<()> = Term::with_height(TermHeight::Percent(90)).unwrap();
    let _ = term.clear();
    let _ = term.print(0, 0, "Hello world!");
    let _ = term.present();
}
```
Line one initialized the terminal space you will be using. TermHeight sets how high you want the terminal to be. The second line clears the screen for you. The third line tells TUIKit what text you want to print, and where to print it. Line four is where TUIKit takes everything you have given it and displays it.

Please note that before today, I have never used it before, so this may not be the best way to do things. The documentation on this framework is sparce so this may not be the best way to do it. I am iffy on setting the TUI screen to 90% of the terminal space, as I am sure there has to be a module included in this crate that lets it take the whole screen. When I set it to 100 it panics and crashes. I will figure it out.

## Movin'_git

I am now hosting Bibliofile on Gitea, which you can find at [git.whoisthisjoker.com](https://git.whoisthisjoker.com). My reason for this is because I simply do not trust Microsoft to act in my best interest as a hobbyist programmer. With GitHub copilot they are already violating GPL licenses for open source projects, and I am not interested in contributing to that. My new repository might feed Bard, Google's AI, and I am not sure what to do about preventing that. Adding my git to my robots.txt might help some, but there is nothing preventing Google from just ignoring it. 

The bright side is that, AI regardless, if Microsoft decides to get weird with GitHub I will not be affected. It is easy to argue that Github will always remain the same because it hasn't changed too drastically since it started, outside a few new bells and whistles. It will not stay the same though. Big Tech in 2023 is constantly making changes nobody likes, and frankly I think it will eventually get to Github. Copilot is already an iffy change that upset a lot of people.

The problem with the modern internet is that it is too centralized...everyone hosts on GitHub, or if they are hipster, GitLab. By hosting my own, I can continue contributing to open source and not contribute to the constant centralization and potential censorship that causes. 