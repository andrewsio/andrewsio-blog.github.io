---
title:  "So Long, Squarespace"
date:   2020-01-02
layout: post
categories: blog
tags: new-year blog 2020 blogging squarespace jekyll github github-pages markdown
image: /assets/img/new-blog.jpg
---

Want to hear something frightening? Since I moved my blog to Squarespace I have given them $1,210 dollars. **That is INSANE.** It's enough for a trip to NYC!  

Time for a change and today I'm very pleased to welcome you to my new blog which as you may have noticed looks remarkably similar to the old blog. The key difference if that it no longer costs me $19.20 a month to host but it also now fully supports Markdown, can be updated and drafted locally and allows me to stay in control of my content.

I signed up for Sqaurespace in October 2014 after moving from Wordpress where I believe it was hosted on a small VPS server I was paying for. [Here is what it looked like back then][1], not much but it was something. The hope by moving from Wordpress to Squarespace was that I would focus more on content creation than screwing around trying to keep Wordpress patched and secure. The additional cost of moving to Squarespace would also work as an incentive to actually write blogs more frequently too. It's fair to say that mindset worked I've got a fair few posts in the collection, some which I love others which are just a snippet into the past. I'm confident that I'm invested enough in content creation and I cannot wait to write more this year so the 'blog tax' can stop.

The new blog is hosted on [Github Pages][2] which has become a bit of a go-to for hosting small websites, the combined integration with Github is very useful for tracking changes and over the past few weeks I've learnt a lot about how Github works. The site itself is built using [Jekyll][3] which is a static site generator, a process where the programme runs through all the content, templates, etc and outputs a flat html site. Github Pages has native support for Jekyll so all of that happens in the background so long as the raw content is uploaded correctly.

Jekyll can also run locally on my MacBook which allows me to store and draft all posts and changes locally before committing to GitHub. This feature would have been hugely helpful when Owen and I were on the [#TrainToTurkey][4] where connectivity to the internet was very patchy. Of course it was possible to draft in Markdown and then copy/paste to Squarespace but I then had to mess around with images when I had a connection, now I can do everything and just hit commit when I'm ready - easy!

The theme for the blog is a fork of a theme by [LeNPaul][6] called [Lagrance][5] which was pretty simple to interact with and very close to the theme I was using on Squarespace. I have adjusted a bunch of things in the CSS file but nothing major. I have added the [jekyll-redirect-from plugin][8] so I can keep my slugs working from the old site, I don't know how much these are used but I know some of the posts reference other posts so this will save updating them. Another feature I added was some code and a script from [Long Qian][7] which allows me to keep tags working too, this is a very clever little setup that I'm a huge fan of!

Moving all of my posts has been a bit of a Christmas-break challenge, I'm about half way through and expect to have the remainder completed before Squarespace is finally switched off in late January. So far I have moved all of the posts from 2018 and 2019 most of which were very content rich. There was a resonable amount of manual effort to move things, but I was able to cheat a little by exporting an XML from Squarespace, importing that to a free Wordpress site. Once in Wordpress I was able to bulk-download the media and use a [script I found online][9] to convert the posts into Markdown. Once in Markdown format I just review each post manually and add tags, and correct the image URLs. Not too bad... The benefit is that I'll have a nice clean content-set for the future.

[1]: https://web.archive.org/web/20140516235017/http://andrews.io/
[2]: https://pages.github.com/
[3]: https://jekyllrb.com/
[4]: /tag/traintoturky.html
[5]: https://github.com/LeNPaul/Lagrange
[6]: https://github.com/LeNPaul
[7]: https://longqian.me/2017/02/09/github-jekyll-tag/
[8]: https://github.com/jekyll/jekyll-redirect-from
[9]: https://github.com/lonekorean/wordpress-export-to-markdown
