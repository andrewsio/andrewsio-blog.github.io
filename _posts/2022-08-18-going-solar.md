---
layout: post
categories: blog
tags: solar
title: Going Solar
date: 2022-08-18 00:00:00 +0000
history:
location: High Halstow, Kent, UK

---
Exciting news! We've committed and we're going Solar. A fair amount changed since the last blog post, reading it back, neither company that we were talking to were particularly interested in our needs as a customer; the council scheme was slow and it turns out they couldn't wait to get us off their books, and the other one, well, let's not go there.

Just after posting the last blog I got a call back from [JPS Renewable Energy](https://jpsrenewableenergy.co.uk). We had a home visit from a member of their team and spent time talking about our needs and the technology that they recommend for our situation. All very positive, Ross who visited listened to our needs and built a proposal accordingly. JPS used [Open Solar](https://www.opensolar.com) to present the proposal which made it really easy to see the different options, associated cost and an estimated break even date.

After the visit I sent Ross and email late in the evening with a LOT of questions, I was very impressed to see a reply before I started work the next day. Clearly a firm that cares about the customer. We decided to proceed days after the visit.

Since proceeding, the company have a big red banner explaining that they now have a waiting list for enquiries. Clearly we got in touch just in time! We are expecting everything to be installed in November (four months from order) and we're keeping our fingers and toes crossed.

Here's a bit of a summary on the specification that JPS recommended and what we opted for...

## Panels
JPS recommended [Tiger Neo all-black panels](https://jinkosolarcdn.shwebspace.com/uploads/JKM395-415N-54HL4-B-F1-EN.pdf) from Jinko Solar. Jinko is one of the largest manufacturers of PVs with a significant market share globally, they come with a 25 year product warranty and 30 year performance warranty. The panels are mono-crystalline, [half-cut](https://www.solarreviews.com/blog/half-cut-solar-cell-technology-explained) with 108 cells, rated at 415w and physically larger than those recommended by the other firms.

The panels have some interesting tech; they have n-type cells (as opposed to the more popular p-type) which provides for a higher efficiency out of the box and over time, ([here's an article which explains the difference](https://solarmagazine.com/solar-panels/n-type-vs-p-type-solar-panels/)) and [a great site that explains the science](https://www.pveducation.org/pvcdrom/pn-junctions/doping). Essentially, the silicon is 'doped' with a different element to alter the number of electrons and holes in the semi-conductor. It's expected n-type will become far more popular in the years to come. The panels also feature SMBB technology, which is essentially a round-shaped multi-bus bar (the metal bit in a cell) rather than a typical square, the round shape results in the trapping/scattering of more light towards the silicon and thus further improves efficiency, ([here's an article which explains how that works, and gives some other commentary to the panels](https://solarwithyash.com/jinko-solar-panel/)).

We will have a 12 panel array on the roof, with a total power rating of 4.98kWp, producing a real-world theoretical estimate of something close to 5,000kWh a year. Over a year, this will provide generation of about 40% more electricity than we use today based on our current consumption. Of course we'll produce less than we need in winter and an excess in summer, so even with storage will draw some power from the grid on winter months and on days with low/no generation. In the theory, December should see us produce just under 180kWh/month and the height of July 620kWh/month. It'll be interesting to see the actual real-world results. We use something like 300kWh/month at the moment, we moved in March so probably a tad more in Winter. Generation calculations are based on the EU application linked in my previous post.

The panels will each be mounted in a vertical orientation on the roof, in two rows of six. To help place them centrally and to avoid any shading we will have the chimney removed (which we don't use). JPS will have the scaffolding installed a week in advance to allow for the chimney removal. The panels will be mounted on top of the roof tiles and so we will also have bird blocker skirt added. With all 12 panels we will have about 250 sq ft of PV on the roof, taking up most of the roof.

I still don't think this will be enough, once we have an EV or two, install an ASHP, air-conditioning and have a grown-up daughter we won't have enough capacity. All of that will happen in the next ten years, so within the life of the system. We should however have additional roof space available on the extension which should give us and extra 30/40% of roof space, about what we would need. What's more, we could take the opportunity to sink the panels into the roof to free up the weathered roof tiles for the extension. sinking panels into the roof looks WAY better but not worth the additional installation cost unless there's construction/roof work going on.

## Inverter
This was a big change in thinking.. JPS were quite up front in recommending [Enphase micro-inverters](https://enphase.com/en-gb) rather than a string inverter. There's lots of resources online comparing micro-inverters to string inverters so won't cover here. Essentially, micro-inverters are a small box which sits behind each panel to convert the DC to AC, principally eliminating the need for a single large unit that does the same and in doing so removing the need for DC current to run through the full string of PVs.

There's a few advantages which I really like:
1. The inverters are managed centrally but all function independently with the management system providing performance reporting and isolation control.
1. If an inverter fails, only one panel is offline instead of all of the panels. Since each inverter is handling smaller loads, there's less stress on components and in theory a longer life.
1. There is no need for an enormous and possibly noisy inverter box inside the house or loft. The inverter is behind the panel, so it's all out of sight.
1. If we want to add more panels, we don't need to upgrade or replace the string inverter, we just add more micro-inverters. We would however need to re-apply for another G99 if we add capacity and want to export it. It is possible to limit in software how much to export if necessary.

There's also some theoretical benefit for shading and leaf cover issues, where with a string inverter shading effecting one panel impacts the output of the whole array. I've seen videos online calling those claims into question and proving that it's not true of modern half-cell split-module panels. Frankly, not really a concern since we're unlikely to experience any shading.

There are some drawbacks:
1. If something does fail, replacement or repair is going to happen on the roof, that's not ideal as it'll probably need scaffolding or access equipment.
1. Micro-inverters are certainly more expensive than a simple string inverter. Probably comparable in cost to a string inverter with panel optimisers.

Enphase seem like a very sensible manufacturer, they're US-based with a good online community, with a mature product line and a big market share, particularly in the US. The devices all have a 25 year warranty, with a UK company presence too, so no issues there. The [Enphase app/portal](https://enphase.com/en-gb/installers/apps) looks great too and JPS showed a real-world example of an installation, with each inverter reporting it's output easily showing past performance over time too. There is an accessible API and code on GitHub to connect to HomeAssistant, etc. The small little control box will sit in the under-stairs cupboard along with the alarm and distribution panel.

The model we'll be installing is the [IQ 7A](https://enphase.com/en-gb/installers/microinverters/iq7a), we'll need 12 in total, one behind each panel. The gateway uses CT clamps to monitor the consumption and production and supports ethernet for connection to the network. I believe that they inverters use Powerline to communicate with the Envoy Gateway, so there's just a AC cable which needs to be installed between the roof and the consumer unit/meter.

The micro-inverter spec sheet seems to explain that a maximum of 10 units can be installed per section or per 20A circuit. But to be honest, I have no idea how they will be connected together. Speaking of which I also have no idea how we're going to manage the cable between upstairs and downstairs. It would have been ideal to install the cable in the exterior wall cavity, but we've since had insulation installed so that might not be possible. We'll wait for the survey to complete to understand. really hoping that we don't have to have a cable present externally as that won't look very good.  

## Storage & AC-Coupled Inverter
JPS recommended that we go with the [GivEnergy](https://www.givenergy.co.uk) product line for storage. GivEnergy are a UK-owned battery and inverter manufacturer with manufacturing in China with good presence and established local market share. JPS were quite up front explaining that our current needs don't necessitate much of a battery with an over-sized array. Before I really started researching I was expecting to at least install a battery which matched our daily consumption. I think over-rating the battery will be good, to help with odd days where there is low/no PV generation.

We opted to install the [Giv-Bat 8.2](https://www.givenergy.co.uk/pdf/Version%202.0/Giv-Bat%208.2.pdf), a relatively new product in their lineup and the second largest battery on offer. It has some unique features typically only seen with the premium options on the market:
1. It offers 100% depth of discharge, so we're getting all of that 8.2 kWh. Apparently it is a 10 kWh battery inside the box.
2. It offers 10 years of unlimited cycles, so we can go to town on charging and discharging.

It is a bit of a unit at 94kgs but will fit in the under-stair cupboard just fine sitting on the floor. The battery has the trendy LiFePO₄ cells and operates at 51v DC. So it is plenty modern and should hopefully last some time. What it doesn't have that some of the fancy options do have is a backup capability, allowing for the battery and PV to operate the local circuits in the event of a mains outage (like a UPS). While it would be good to have this, we haven't really experienced many outages and I expect that with the increasing adoption of solar it will be something that can be retrofitted later once more options and demand exists on the market.

Because we're opting for micro-inverters we will need to install an AC-coupled inverter to take the excess solar and charge the battery. The same inverter will convert the stored energy back to AC when we're drawing from the battery. [GivEnergy offer a 3Kw option](https://www.givenergy.co.uk/pdf/Version%202.0/AC%20Coupled.pdf) which is fairly straight forward. These devices aren't cheap, well, they're cheaper than the battery! But an important component in the system. Yes, there will be some efficiency loss with the conversion that's not seen with a hybrid inverter and a string of panels, but I'm fine with that.

The 3Kw rating means we can draw a maximum of 3,000w from the battery (e.g. a high-power kettle) and anything above that comes from the grid assuming the PV isn't producing. Our consumption profile shows us very rarely consuming >3kw and we would adjust accordingly anyway, such as using the tumble dryer only when it is sunny. On the same line of thought, we're going to be charging the battery at a maximum of 3kw, so it will take us about three hours to charge from 0% to 100% if we needed to (I think...) assuming we have the excess to do so.

The inverter only comes with a 5-year warranty but is upgradable to 10-year with an additional cost of what I think is probably about 25% of the cost of a new unit. We opted not to take that on and will take the risk. Were it to fail after year five then prices for this would have probably reduced and I expect there will be improved products available too.

The inverter is smaller than the big inverter needed for a PV array, so can fit quite easily in the under-stair cupboard too. The GivEnergy platform also has its own app, online portal and open API.

## Diverter
We mulled over whether it was worthwhile ordering an [Myenergi Eddi](https://myenergi.com/product/eddi/) but decided in the end to go for it. This is a device which diverts excess PV energy to an immersion element in the hot water tank, negating the need to use the gas-fired boiler to heat hot water. That excess PV energy would instead be going to the grid, earning not much money. There are a few different systems around, iBoost, Solic and the Eddi. They all do essentially the same thing, but with different hardware/software.

We have a gravity-fed system in our 22-year old house. That was a desirable characteristic for us when we bought the house specifically because it will make installation of a diverter and later an ASHP installation easier. Yes, we may need to upgrade the boiler, hot water tank, etc, but that will be much simpler since the pipework is all in the right places. Our old house had a mains-pressure combi-boiler system and wouldn't have had the option of installing a diverter in this way. I also like the fact that if there is a mains water outage we have a limited supply of fresh water stored in the loft cistern. And yes, supply does fail and an incident [recently affected people on the Isle of Sheppy](https://www.bbc.co.uk/news/uk-england-kent-62148068) for several days during the hottest week of the year - no thanks!

Our hot water tank does need replacement soon, but not immediately - it'll be something we think about when we add another bathroom or en-suite, possibly as part of the extension work. We also need to install a new shower pump and probably increase the capacity. For now, we should be able to install the Eddi and connect it to the 3kW top-mounted (not ideal) immersion element. There is something connected at the bottom of the tank, but I don't think that is an immersion element, but some kind of temperature probe - could be wrong. We've actually never used or tested the immersion, perhaps I should see if it actually works. If we were to upgrade, I love the look of the [Mixergy hot water tank](https://www.mixergy.co.uk) which uses a fabulously simple concept to simply heat just enough water and smart technology to plan for demand. Here's a [good video on how Mixergy tanks work](https://www.youtube.com/watch?v=z1Z4JCoPAGc).

The Eddi will connect back to a Harvi device installed in the under-stair cupboard so it can determine when it should consume excess power as the storage battery will also be trying to do the same thing. This is all wireless, but I have installed an ethernet cable just encase anyway.

Our neighbour has a solar array and he also has a diverter installed. He said that in the summer months he basically doesn't use gas at all, just paying for the standing charge. This is good news, since heating hot water costs us about 36p a day, plus 26p standing charge for gas connection.

## Future Thinking on Heating

Keen in the years to come to move to an ASHP, I have a romantic idea of a wood-burning stove with an integrated boiler (such as the [Woodfire CX8](https://www.stovesonline.co.uk/wood_burning_stoves/Woodfire-CX8-boiler-stove.html)) sitting in our downstairs living space. The stove from that boiler could assist with hot water production and central heating in the colder, winter months where efficiency of the ASHP is poor and solar production will be very low or possibly zero if it snows! I think those wood burners look really good and so some something to consider for the extension, along with how we would install a flue, possibly taking advantage of the natural air flow to hear our upstairs bedroom too. If we do take this I think we'd need a separate thermal store in addition to the hot water tank, some thinking on [how that might be achievable here](http://www.heatweb.co.uk/w/index.php?title=Integrating_Heat_Pumps_with_Thermal_Stores), essentially a plate heat exchanger is needed to produce hot water because ASHP would operate at a low temperature. Overall our goal is to remove entirely our dependence on gas as a heating source and to reduce the need for high electricity consumption through the ASHP during the winter months when generation is low.

But that's the thinking... We'll stick with Solar for now. The rest can wait.
