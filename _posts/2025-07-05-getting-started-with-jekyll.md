---
layout: default
title:  "Getting started with Jekyll"
description: The firstest post ever!
date:   2025-07-06 00:26:00 +0200
categories: jekyll
---

# So I guess I should write a post eh?

Well, it's been a while. I'm writing this here to myself just on the dev branch but, hopefully I'll have this published properly soon.

## Why Jekyll?

I love free software. All these amazingly powerful tools, freely available, have been a big part of why I enjoy fiddling with computers.  
I'm not much of a programmer, but I enjoy learning. Computers can be overwhelming too, but it's great when you can take it at your own pace.  
With Jekyll, so far (And I'm still just taking baby steps) I've been able to get into web stuff, without having to bite off so much at once. It seemed to allow people to both get started while having to do very little, as well changing things to make it become theirs. Perfect match for me.  
It's been a name I've heard of for years, though never quite looked into until more recently. Still, it being this mature of a name, as well as it being free and so available, also has led to a lot of community resources and knowledge to be found googling around for whatever it is I want to do, or need to fix.  


(And hey. Markdown is neat, and something I use frequently thanks to Discord)

## What I've tried so far

I initially didn't plan on dealing with posts (ironic) since I first of all figured I just want a place to make available when I Write Things:tm:, which I would do on occasion on Discord, like related to games and whatnot. And this way maybe what I've written could reach a few more people, as well as being easier to find and reference.

Though, this ended up being, well not the first time, that I wanted to do things a certain way, even though most people did it differently. And as I went on it eventually got to me why others don't do it this way.  
Pages are neat for things that are static. Home, index stuff, about, contact, all that. Uses beyond that too. I kinda didn't want to deal with adding dates to my posts, especially for a few things that I had already written and just wanted to make available.  

I looked around a bit for a theme I liked, and found [Cayman][cayman-theme-gh]. It seemed clean and fitting for how i wanted to do things.  
It didn't have any other layouts beyond just `default`, but I figured that was fine. I would have to make my own layouts to make all the [Liquid][liquid-gh] stuff work, so that I could systemize things. I wanted to have categories for what I published.  
The main issue I ran into, after manyt hours of just very basic structuring of things, was that I couldn't quite make use of the attributes of a page in the way that I wanted. I had set up a collection (to keep things separate), and I wanted to make index pages for all pages within a category. And while you can set and fetch a `page.category`, this `category` was simply a custom attribute. I could fetch all the pages on the site, and then check if a post matched the current category, and I did do this initially. What I couldn't do, was specify a category and get all pages within said category with something like `for page in site.CATEGORYNAME`. Something that posts could do.  
I mean, it's a computer. And computers do what they're told to do. I just didn't/don't know how to make it do that. And given that posts could do it the way I wanted, and quite simply so at that, I did realize I should abandon my initial plans to stick to only pages, and just embrace posts instead for the most part. And honestly, I do agree that it's important to have dates on things like these.  

## What I have to do in the future

Is a couple of things. Mainly I'll have to deal with pagination, to avoid index pages becoming a mess, both to navigate in general, and performance-wise.  
I also currently don't have any dates shown anywhere on posts, and any form of sorting on items in an index, something I'll also have to work out soonish.  
I'll also want to change the way my category pages are set up, and ideally make some sort of generator plugin, so that I can avoid having to include blank placeholder page .md files and folders there just to display the index. In the longer run especially this would suck, since I'd have to keep making these for each new category I post something in. It also honestly doesn't make the repository look particularly pretty.


### Wrapping up
I'm usually not that bad at these but right now I can't think of much. Hoping this ends up looking alright/reading alright (It did not end up looking great. But I hope I can better my formatting over time).  
Bye \<3


[cayman-theme-gh]: https://github.com/pages-themes/cayman
[liquid-gh]: https://shopify.github.io/liquid/