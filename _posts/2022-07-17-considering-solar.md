---
layout: post
categories: blog
tags: solar
title: Considering Solar
date: 2022-07-17 00:00:00 +0000
history:
location: High Halstow, Kent, UK

---
We've been in our new home for just over four months now and have really begun to settle in. In the first few weeks we did some decorating, replaced the carpet, curtains, lights (every bulb was incandescent!) and even had a new front door installed. Those changes made a big difference both in how we feel in the house, but also in the energy cost.

Since then we have been putting some thought into how we can improve things further for the future. There's quite a few things on our list, but one thing we're really thinking about at the moment is going solar. One of the benefits to this house is that the rear is south facing, (specifically, 208°/SSW) with a ridge line in the centre, sloping front and back. This would make it ideal for panels and mean they wouldn't be visible from the street. Our next-door neighbour has the same house type with the same orientation and he had solar installed some years ago with good success. Here's a picture of our roof:

![](/assets/img/considering-solar-3.jpg)

We would only use the top part of the roof for solar. The chimney we hope to remove, because we don't use it, don't need it and don't want to deal with the hassle of it!

## Our Journey So Far

Just before we moved in we signed up for a council run group buying scheme called 'Solar Together'. We didn't hear anything for about two months, but eventually we were given a proposal and the name of the nominated provider, Senergy Direct. We agreed to the proposal which required a £150 deposit, and requested the battery storage too since buying it at the same time as the panels means there's 0% VAT liable. I think there was actually the option to select different sized batteries, but can't remember. Details of that proposal below, which I thought was actually quite reasonable.

![](/assets/img/considering-solar-1.jpg)

Another two months goes by and we get another email explaining that the originally selected supplier of the scheme has opted out (because of component shortages) and that a new supplier has been selected, Home Energy Direct. A new less expensive proposal was provided but the size of the battery was reduced to 3.2kWh (no idea why..._).

![](/assets/img/considering-solar-1.jpg)

Things then went quiet again...

Getting slightly tired of waiting, I called up a firm that I saw were installing to some other houses locally, Fresh Electrical Solar. They arranged an appointment for about a weeks' time for a survey. The survey was essentially an hour long sales pitch, which to be honest wasn't really my cup of tea. They provided a quote there and then for 12 panels, a hybrid inverter and a 2.6kWh battery. The cost they provided me was quite a lot more, so we left things there. I was offered finance to help if I needed it. (Seriously, paying money to save money is a very silly idea). They seemed to have a large customer base and for what it's worth and clearly have done a lot of the installations in High Halstow. It could have been the part of the pitch, but they claimed to have negotiated improved lead times of the supply of both batteries and panels, although the battery would be a few months behind the panels.

Last week I got a call from Home Energy Direct, the new supplier from the Solar Together scheme, I was busy at the time but they're going to call back this week. Fingers crossed things work out there...

Since then I've done a little bit of research into what I think we need, but welcome input from those with more experience..

## Our Need
At the moment, we use about 9kWh of electricity a day on average, which varies significantly based on if we're doing the washing. We can use as little as 5.5kWh and as much a 12kWh, we usually use more electricity in winter, but that's typical so that average of 9 will probably come up as we get through the year. Here's a [twitter thread](https://twitter.com/14zz4/status/1447501790820372481) with some analysis I did in our old house (we seem to use less electricity in the new house - yay!). I need to setup EmonPi in the new house, but have our smart meter as a rule of thumb.

Not exactly sure what's led to the reduction, we've stopped using the tumble dryer for anything other than towels and generally have fewer lights on (the house is naturally lighter). We also have a much smaller cooker in the new house too which probably has quite a big impact.

## PVs
12 panels seems to be a sensible number based on the size of our roof and to provide for most of our need most of the year. 12 panels will in theory generate about 5000kWh a year ([according to this EU website](https://re.jrc.ec.europa.eu/pvg_tools/en/)), with an average day in July generating 20kWh and an average day in December generating 6kWh. Based on [Edent's helpful blog](https://shkspr.mobi/blog/2020/04/comparing-solar-panel-generation/) of a similarly sized installation helps support that as a reasonable estimation. Do check out [his automated twitter account](https://twitter.com/Edent_Solar) by the way!

Regarding panels themselves... I have not looked at brands, the council providers both recommended JASolar panels. These seem surprisingly inexpensive looking online, at about £115 each ex VAT. Fresh Solar recommended a different brand "German engineered" but they looked comparable in spec and cost. These obviously need mounting to the roof some how!

I have no idea if there's value in getting a specific type of panel, but suspect there isn't and that so long as it is relatively modern we should be okay. Some seem to have better warranties, but I'm not sure how important that it.

## Optimisers
I'm not certain we need these, our roof is not shaded at all, but they sound like a good idea and I welcome the ability to monitor the performance of each panel. The two major brands available seem to be SolarEdge and Tigo. The SolarEdge optimisers seem to need a supporting SolarEdge inverter. The Tigo optimisers appear to be able to operate independently, with a CCA (Cloud Connector) and TAP (Access Point). There's several models, but the TS4-A-O allow for monitoring, shutdown and optimisation of each panel. Tigo optimisers are about £38 each ex VAT, so not a small cost (plus the CCA and TAP). The council scheme lists both options, but no costs. Decision on the inverter seems to input into optimisers.

## Inverter
There seems to  be two main categories here, assuming the decision to use battery storage. A hybrid inverter, which connects the panels, battery and grid together (DC-coupled) or split inverters, where there's an inverter for the panels direct to the AC/grid and then a separate battery inverter (AC-coupled). [The SolarEdge website has a good explanation](https://www.solaredge.com/uk/solaredge-blog/dc-coupled-vs-ac-coupled-pv-systems). Hybrid is most efficient since there's fewer conversions between AC/DC and so less energy loss.

Since we're definitely intending to install battery storage, the hybrid route seems most sensible. Knowing next to nothing, the Solis option looks decent (RHI-6K-48ES-5G), which comes in at about £1,160 ex VAT on some websites. This apparently has an off-grid backup function (not of particular interest to us) and supports a wide number of storage systems. The other option looks like the SolarEdge system, but these seem more expensive and more limiting for the type of storage that can be connected. The app on the SolarEdge system looks a lot better compared to Solis and much more easily interpretable. Several people on twitter seem to have this system.

Suppose it's worth noting that having good reporting on the app is a pretty important, knowing how well the system is working will allow us to optimise how we're living with it.

The council providers have recommended several different inverters, GroWatt as the default, but options for SolarEdge and Solis. Fresh Electrical listed GivEnergy Hybrid with a paired storage system (although mentioned using SolarEdge optimisers?). The apps for GroWatt and GivEnergy looked okay, but not great.

Probably need to do some more research on this, there's a lot of options and not something that's going to be cheap to change in the future. One thing to consider is that we may add additional PV in the future, possibly on the roof of an extension if we build one, possibly on more of the existing roof, so sizing appropriately now is important to avoid replacing the inverter later. That extra PV would help with an EV when we inevitably buy one in the future.

## Storage
I genuinely have no idea what capacity we would need in a battery (help appreciated!). Like most people we tend to use most electricity in the morning and evening. In the weekend when we have higher usage it tends to be during the day. I have 5kWh in my head, which seems like it would be the right starter amount to cover our usage outside of daylight hours, especially in the summer possibly less so in the winter. I like the idea of having a battery system which I can expand if necessary. I'm not particularly interested in using the battery to charge from the grid during off-peak hours, so think we just need to right-size for our needs.

My understanding is that a battery would do two things for us, targeted at reducing grid consumption. 1. absorbing surge demand (e.g. boiling the kettle). 2. supplying demand while the panels aren't producing.

Options in the storage space seem to sometimes be tied to the inverter choice. The council scheme listed the PylonTech battery which from what I can see looks pretty sensible and the Solis inverter supports them, as I'm assuming does the GroWatt. It is scalable with additional modules and reasonably sensible in price. The Fresh Electrical lists the GivEnergy battery, which is part of the GivEnergy product line.

Fresh Electrical suggested only 2.6kWh of battery, which I really do think is inadequate. There was no calculation done to determine that as our requirement. The Council proposal I think I selected 4.8kWh and it was reduced in the updated proposal automatically.  

There is of course the Rolls-Royce option in the Tesla PowerWall, which isn't an option for us. It'd be overkill for our needs and too expensive for our pockets!

More research probably needed...

## Other
During the summer months we're going to be generating far more electricity than we need. While exporting obviously generates some offset against cost, it seems more practical to put that excess energy to better use. There's two products, one called [iBoost](https://www.marlec.co.uk/product/solar-iboost/) and another called [Eddi](https://myenergi.com/eddi-power-diverter/) which divert energy to the immersion of a hot water tank to heat that instead, reducing gas usage. Seems like a pretty sensible idea. It would be easy to adjust our hot water schedule to allow for this kind of device to operate.

Interestingly the Fresh Electrical rep said that they don't install these, instead they just suggest that people turn the immersion on/off on a sunny day since that will use generated power anyway.

We will probably park this idea initially, our hot water tank needs an upgrade at some point, so it's probably worth waiting. We might even look at a product like this smart [Mixergy tank](https://www.mixergy.co.uk) when the time comes.

On a slightly separate note, we have a company visiting tomorrow to quote for cavity wall insulation. This house was built in 2001 and should have had it installed, but it seems that it didn't (naughty). Many of the houses around here have had it installed afterwards, including Dad's. No idea how much that might cost, but I guess we'll find out tomorrow!

## In Conclusion
We'll wait to see what the council provider come back with when they call back this week about the PV/Storage. I'm relatively confident that I know what we want, enough so to express so anyway. I think the trouble will be that I may be seen as a difficult customer in an environment where there is tons and tons of demand. I think they represent good value, but not certain - compared to the Fresh Electrical quote they certainly do, probably worth us getting another to confirm.

One thing that we need to be really careful with is not overpaying for solar. At the end of the day it is simply a technique to offset future cost, to save money, it has no function as an investment. Perhaps "Being Green" but that's all. We need to not rush, make sure we're getting the right thing and be confident on the costs.

If anyone knows a dependable installed in the Kent/South East way, do let me know...
