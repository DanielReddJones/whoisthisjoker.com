---
title: "What_a_month"
date: 2023-06-28T14:31:17-05:00
author: "Daniel Jones"
tags: [
  "Rust", "programming", "cars",]
categories: ["personal_projects", "personal",]
---

## Storms, broken cars, power outages, and more

This month has been absolutely insane. At the beginning, my car broke down. Twice. Once it wouldn't crank, the second time the engine nearly blew. Both ties it turned out to be a minor fix that the mechanic barely even charged for.

Then once all my car issues were resolved, stormageddon happened and took out the power in parts of Texas, Louisiana, and Arkansas. I was unfortunate enough to be caught in that storm.

Hopefully, knock on wood, nothing else insane happens in the two days we have left of June. Now that everything feels settled, I have resumed work on Bibliofile.
Today, I switched the HTML parser from [Soup](https://docs.rs/soup/latest/soup/) to [Scraper](https://docs.rs/scraper/latest/scraper/index.html). Soup was about to be stop working entirely because the author of the library stopped maintaining it, and the way it did several things it was about to make it stop being supported by RustC. My two options were: start maintaining the library myself, or just switch to a different library. I decided that switching to a new library was worth the trouble.

It took me a bit to get it updated. Soup automatically parsed the entire page, but Scraper asks that you specify what tag you want to parse and saves that within a vector. I specified that I wanted everything within the HTML tags to be parsed (thats \<html> and \</html> for those of you that don't know the language) and then I had to iterate through every item within the vector and output it to the terminal.

I have a four-day weekend this week, and if nothing goes wrong HOPEFULLY I will be able to do what I said in my last blog post and actually finish it. The plan is that I will switch from ncurses to TUIkit, as TUIkit is more compliant with Rust's memory-safe requirements and will feel less "hacky" getting it to work.
Once that is done I will implement a menu system that will allow a user to add books to their library, and select which ones they want to read. This will be more intuitive than adding a book via commands.

My next blog post will be posted on Tuesday night explaining whether I was successful or not in releasing version 1.0. Again, assuming the Lord is willing and the creek doesn't rise. Stay tuned.