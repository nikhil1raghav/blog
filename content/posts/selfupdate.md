+++
title="Self updating readme on github"
description="How to create a self updating readme on github using github actions"
author="Nikhil"
date="2020-10-25"
tags=["python", "automation"]
+++
Recently created a readme for my profile on github, found out all kinds of things you can automate using github actions and reflect them on your readme, like followers, stars, self updating profile links or a feed from your blog.

First of all those who don't know about it, if you create a repo with the same name as your username on github, it will act as a README for your profile. So if you haven't created one yet, go create it. It is like instagram bio on steroids.

So once you create that readme there are chances that some of the data you entered will not remain same over time and maybe the frequency of change is too rapid that keeping the readme updated becomes a problem in itself. For instance, social media handles change, or if you have a youtube channel or a blog it would be interesting if that RSS/Atom feed can be shown directly on github and updates itself regularly, even all your recent releases and contributions can be shown using github's GraphQL API. For that you can use a github actions.

For this I wrote a simple script in python `build_readme.py`, only explicit dependency it needs is the `feedparser` library. It hits my blog's RSS feed and retrieves the link to 8 most recent posts. Code is pretty simple and explanatory, I used regex to identify where is the blog section markers in my readme and that chunk is updated when you run `build_readme.py`. After you create a similar script for yourself, the last thing you need to configure is `build.yml` file in the workflows directory. Mine is set to run the action on every push and every day at midnight.
