---
title: "Frankfurt"
date: "2013-09-14"
layout: post
categories: blog
tags: germany frankfurt travel work
image: /assets/img/import/8e5fa-img-20130817-00002.jpg
redirect_from:
  - /blog/9
---

I'm not sure when I defined number nineteen quite what I had in mind. Whether 'working overseas' includes business trips or if it should only be a permanent job... I've given it some thought, and decided that business trips should count. I work for a global organisation after all, so what more would I want? I'll leave the aspirations of working for a crazy oil rich Arab for another day, with this post officially marking another one off the list. Now, to tell you all about it! We've got lots of Extreme switches out in the field, Extreme are good, very good and even [LINX use them on their second LAN](https://www.linx.net/service/publicpeering/extreme). But good as they are they're certainly not easy and simplicity is fundamental for keeping a large network running smoothly. With such a big footprint it's a mountain of work for me keep on top of when they fail, let alone keep upgrades rolling and ensure that any problems are dealt with. So how do we fix that? Cisco. Everybody in networking is familiar with Cisco, it's ubiquitous, well documented and proven. In addition to all of those good things they're not painted a hideous shade of purple - definite WIN.

![][photo-1]

And that's how this journey began; the first office elected to be upgraded was Frankfurt. It just so happened that one of our DC engineers is also based there, which is handy as he's a top lad. In addition to upgrading the switches we also decided that it would be good opportunity to consolidate the number of routers we have in each office, typically there are 5 individual routers, two cisco 18xx routers for the primary link, one CPE from the provider and another of ours, then three Cisco 871s for the backup line, one terminating SDSL, another from our MPLS provider and ours. All a bit mad and all adding to the likelihood of something failing. Instead we would run IGP between the carrier directly on the 3750s and get rid of our two routers. EIGRP was selected as our IGP although I'm not entirely sure why, but hey, I'm cool with EIGRP so why argue with a good thing.

![][photo-2]

Shooting forward a bit, 3750s all configured and shipped out, here I am at Terminal 5. I must make a small confession; I've been gagging to travel out of Terminal 5 for ages, but holidays are always from Gatwick and the domestic flights I've been on with BA are always Gatwick too. In addition to T5 I was particularly looking forward to going on the Business parking pods, which drive themselves from the parking to the Terminal (which is freaking awesome! but very, very geeky). If you have patience enough to trawl back through my twitter history you'll find many tweets about this since I got there particularly early in order to mingle around.

![][photo-3]

Once I'd landed in Frankfurt one thing noteworthy is that the taxi between the runway and the gate is INSANELY long. Seriously, we must have been trundling along for 20mins. The airport was pretty cool though, massive but easily navigable. I know I probably say this with every travel related post I've ever written but Frankfurt is definitely a City worth visiting. The many tech-related travel books I've ready everyone seems to slate Frankfurt as this pointless metropolis just there because it's in the physical centre of Europe. They couldn't be more wrong, there is loads of culture, an awesome river and all sorts of stuff going on. The first evening I spent the Frankfurt football team were playing Munich and despite Frankfurt losing there was live music, beer stands and all sorts going on. The second night I managed to find an Apfelwein festival, the live music was a bit better, with an Elvis tribute act playing until late. No complaints were had from me, except maybe a sore head the next day.

The installation went well, although the provider was somehow unable to configure EIGRP authentication but that's no biggie, probably would have ended up being a PITA anyway. The only other issue we had was with the port channels, I don't get why but port channels just don't like being preconfigured. Re-applied the config and it was fine.

![][photo-4]

Another cool thing about Frankfurt is the train station, it's the second largest station in Europe and I probably spent at least 4 hours there. Loads of strange trains, double-deckers, ICE trains and even an old German steam train. I managed to get myself to the Airport on the S9 regional train and even had a quick trip on the Metro - which is especially strange and for some reason doesn't have any ticket barriers (could you imagine that in the UK?!).

[photo-1]: /assets/img/9fe96-img_20130817_041826.jpg
[photo-2]: /assets/img/8e5fa-img-20130817-00002.jpg
[photo-3]: /assets/img/fb7e9-img-20130818-00016.jpg
[photo-4]: /assets/img/bdde2-img-20130818-00013.jpg
