+++
title="Private search engine in 5 minutes"
author="Nikhil Raghav"
cover="sear.jpg"
description="Create and deploy your own searx instance"
+++

Every non privacy respecting search engine out there logs your search history to profile you and target you with more personalised ads, sometimes that also leads to a self created filter bubble.

[__Searx__](https://searx.me) is a metasearch engine available under GPL 3, which compiles search results from more than 70 search engines. Fun fact is you can deploy it locally and enjoy searching from your customised search engine. I'll walk you through the deployment.

#### 1. Clone the repo
```bash
[nikhil@nikhil]$ git clone https://github.com/searx/searx.git
```

#### 2. Install dependencies
```bash
[nikhil@nikhil]$ cd searx
[nikhil@nikhil searx]$ ./manage.sh update_packages
```

#### 3. Run it
```bash
[nikhil@nikhil searx]$ python searx/webapp.py
```
Now a local instance will be up and running on port 8888. Enjoy searching with your own search engine.

#### 4. Some prep

Now if you change default search engine in all your browser to __localhost:8888__,obviously you won't be able to search anything after you reboot unless you run the server manually. For that you can create a cronjob or write a small script in config of your window manager.

You can customise appearance of your searx instance by tinkering with themes, css and other assets in __static__ folder. Searx also supports [bangs](https://duckduckgo.com/bang) like [duckduckgo](https://duckduckgo.com) you can find them in a json file named bangs inside searx folder.

