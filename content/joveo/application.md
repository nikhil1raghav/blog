+++
title="My Application for APM internship at Joveo"
Author="Nikhil"
date="2021-06-21"
math=true
+++

Hi, I'm Nikhil. I am currently pursuing B.Tech in Computer Engineering from [J.C. Bose University of Science & Tech](https://jcboseust.ac.in) and I'll graduate in 2022. This is my application for the role of APM intern at Joveo.


## Why do I want to work at Joveo?

Not everyone is working on interesting problems like cookie-less tracking and offering an internship. I also like the idea of using data-driven decisions to match employers and employee in the times where lot of relevant candidates are cut-off from the process just because a resume parser did not understand the layout of the resume properly.

---

## Why am I a great fit?

Checking some boxes from [here](https://coda.io/@praf11/joveo-product-openings)

- I can communicate my thoughts effectively and I don't know if I have a strong business sense but I do have an eye for aesthetics and making clever design decisions.

- I work hard, love to learn new things and solve problems.

---


## RSS feeds in telegram

As mentioned [here](https://coda.io/@praf11/joveo-product-openings), I would like to share how I created a telegram bot, documenting the process, challenges faced, lessons learnt and some decisions I took to solve some problems I encountered while making a bot that serves rss/atom feeds on telegram.


### Features of the bot

- Extracts RSS/Atom feed link automatically, just drop the link of the website or page that you want to add.
No need to find that elusive rss button or scouring through source of the page to find the link. Just drop the link to youtube channel, subreddit, github repo or anything that supports RSS syndication.

- Sends new messages regularly in an interval of 1 hour, just add the feed and forget.
- Basic CRUD operations, add,delete,update feed links
- BONUS : Telegram has instant view templates for about 8000 websites (you can count number of rows on this [page](https://instantview.telegram.org/templates)), so you can read posts by BBC and follow favourite blogs on medium and read them without leaving telegram.


I created it to promote RSS/Atom subscription method among my friends, idea of subscribing to something without sacrificing your email id or personal information is alien to many people I know.

### Building the bot

Looked up internet to find how people create bots on telegram, my weapon of choice for scripting and such tasks is python because code is concise and there are lot of helpful external modules you can bootstrap on. So, I read enough documentation of pyTelegramBotAPI to get started and creating a simple conversation flow. 

Now to compose a message for the user I would parse the feeds added using `feedparser` and return the entries with a short description, a link to the new post and name of the website that post comes from, so that someone can distinguish between posts from different sources in one feed.

In the first iteration of the bot I was using plain text files to store all user data, which was cumbersome and slow.


- #### Problem 1 : How to not send the same link again to the same user?

	- First idea was that every entry in a feed has a time stamp called publishedDate, I could parse that and compare it with the last time I updated the feed and send the post accordingly. Wrote a simple test script to do the same but data is not uniform across all rss feeds, some use a different time format thus it was not a good solution.

	- Second idea and the idea I went with was to store the links that I have shared so far for every user, so whenever I have to decide which link to share I could lookup if it was sent earlier.

- #### Problem 2 : Non-uniformity across feeds and absence of data
	- Many fields turned out empty in many feeds which raised exceptions a lot of times. Like some feeds would have no description,no title but every feed had a link.

	- So I started sending only the link, because when you send a link in a chat application it does all the heavy lifting of fetching a short description and thumbnail.

- #### Problem 3 : Very slow query time
	- As I used text file to store data, lookups were slow because bot had to check every line to find a match
	- Solved it by using sqlite to store user data and it improved code quality and query time considerably


- #### Problem 4 : Saving database from blowing up
	- As I was hosting it on my mobile phone, I wanted that database doesn't become too big too fast.
	- If an average user adds about 10 feeds, out of them 5 feeds are very active like hackernews, slashdot or a news website. So in the worst case everyday I'll send about 100 messages to each user on average.
	- In one month every user would have received 3000 messages

	- If I want to serve atleast 1000 users who get an update at least 24 times a day then query time of $24 \* 1000 \*log(3000)$ for every update is manageable.

	- Still what I can do is keep the size of database almost constant. Whenever a new link is added I remove the oldest link sent from the same website and only check for a limited number of new links, so that I don't end up inserting the removed link back into the database.


- #### Problem 5 : How to disperse new messages automatically?
	- Created a process in a different thread which will run every hour to check for new posts and send the messages.


### Deploying the bot
Deployed it on my mobile phone on termux, managed it using ssh from my computer.


---

[My Résumé](/files/resume.pdf)

















