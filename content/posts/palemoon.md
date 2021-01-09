+++
title="Big Browser is watching"
description="How I tried to stop using firefox and ended up with two more browsers"
Author="Nikhil"
date="2020-10-10"
tags=["browser", "privacy", "palemoon", "firefox"]
+++

I love minimal software and always try to minimize bloat on whatever system I use. I also like to read too many blogs on internet but you don't need a power hungry and feature rich browser to "just read blogs". So recently, I came across [this](https://www.youtube.com/watch?v=EBWy1d-JE6A) video introducing [BadWolf](https://hacktivis.me/projects/badwolf), which is a minimal [WebKitGTK+](https://webkitgtk.org) based browser that has two very accessible buttons to toggle javascript and images on a webpage and one simple download manager. I know there is much more going on behind the scenes, but this is what that meets the eye first. 


BadWolf is an amazing option to read blogs without unnecessary power and memory usage. Then I visited [BadWolf's home page](https://hacktivis.me/projects/badwolf), it mentioned some blogs and [this](https://digdeeper.neocities.org/ghost/mozilla.html) caught my eye. Don't forget to read it yourself. After reading it I checked myself and found that I don't have any control over how firefox updates itself. There used to be a choice earlier but now it's gone. I've always used firefox as a daily driver and never noticed that it has changed a lot over time. So I replaced firefox with [Palemoon](https://www.palemoon.org) and it is an amazing browser and also allows you to choose what updates to install. If you're a firefox user you'll find yourself at home with Palemoon, all keybindings are same, you can create profiles of your browser just like firefox and all `about: ` addresses work except `about:preferences`. I've used it for two days and here are some good and not so bad things about Palemoon.

# Pros
- Native RSS feed viewer.
- You can add RSS feed from address bar if a website has one.
- Automatically adds search engines you visit no need to add and remove a search bar like firefox whenever you want to add a custom search engine.
- Full blown firefox alternative barring some features (which will be discussed in cons).
- Support for firefox extensions (\*.xpi).
- Browsing history and bookmark section is better organized and easier to find.
# Cons
- No WebRTC support.
- Doesn't support all extensions from firefox specifically __web extensions__.
- In firefox there is a padlock in address bar which is really accessible option to clear cookies and site data. In palemoon you need to do it in old fashioned way by opening page info `Ctrl + I` .
- On some websites experience is not smooth as it is on firefox. For example [competitiveprogramming.info](https://competitiveprogramming.info) lags on palemoon, but runs smoothly on firefox.

After installing Palemoon I configured all profiles as I had in firefox and  thought Palemoon is a solid replacement for Firefox and it is time to say goodbye to Firefox. But then I tried to open Google Classroom and wasn't able to join any meeting. Then I found out that Palemoon doesn't support [WebRTC](https://webrtc.org) for some security and privacy reasons. After all I can't uninstall firefox that easily as I need to take my classes. So here I am with two more browsers installed and waiting for this lockdown to end so that I can uninstall firefox for good.
