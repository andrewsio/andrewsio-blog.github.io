---
title: "A Brief Overview of Firewalls"
date: "2012-11-12"
layout: post
categories: blog
tags: firewall technology networking
---

Back in 1993, while I was busy being a toddler a chap at CheckPoint came up with something called 'Stateful Packet Inspection'. Sounds terribly boring, but it isn't. Stateful Firewalls are the unsung security guards of the internet, here's how they work: A long, long time ago - all we had to protect our networks were packet filters. Packet filters work at Layer 2 (data-link) and 3 (Network) of the OSI Model. They work by examining the header of packets against a rule table, containing source address, destination address, protocol and (in the case of TCP and UDP) the source/destination port numbers. They can be configured to permit (pass the packet), drop (silently drop the packet) or reject (send a failure to the transmitting host).

Wait, that sounds exactly like what a modern firewall does anyway?

Not quite, packet filters just look at the headers of Layer 2 and 3 and match it against a static set of rules. This leaves the risk that traffic could be spoofed or flooded. In addition, because it is a static rule table access must be granted bi-directionally (in most cases, specifically TCP), this means an administrator will probably have to open up the entire dynamic port range for traffic returning to a client. All a bit messy!

Enter 'The Stateful Firewall' a stateful firewall checks packets up to Layer 4 (Transport). By looking at the headers at layer 4 the firewall is able to determine if a TCP connection is being established, is already established or is being closed. The firewall retains this information in the state table. If the connection is new the firewall will run the connection through the security policy and accept/reject/drop accordingly, if the connection is already know to the state table the firewall will skip checking the connection against the security policy, it can do this in either direction, because the firewall will expect the return traffic. Once the connection is closed or if it times out the firewall will remove the connection from the state table. The same applies in a similar way to UDP, a connection log is kept in the state table, if packets that are not part of a recent UDP connection then it is passed through the security policy, since there is no close or finish mechanism UDP connections are just timed-out of the state table.

The benefits of using this technology are quite substantial, not only does it improve performance by only running the connection through the security policy once which saves on CPU resources, it also improves security reducing the ability to spoof addresses and not having horrible holes open in the policy. Win win.

However, with a more complicated process come a few caveats: Time outs; some poorly programmed software applications may not recognise that a connection has timed out on the firewall, likely due to no traffic having been passed. The application would need to be able to recognise that the connection will need to be re-initiated. Another issue is state table overflow; while a stateful firewall is much more efficient it still needs to manage a big table of connections and to be able to update it constantly. There will be a limit to how many connections a firewall can manage at any one time. Should the firewall exceed that limit it will (typically) drop new potentially legitimate connections. This is something that DDOS attackers target as it will not only stop access to one service but any connections traversing the same firewall.

There is another type of firewall that inspects traffic all the way up to Layer 7 (Application). This is called a proxy server, these are very resource intensive but also incredibly secure since they inspect all traffic between two or more networks. Proxy servers act as an intermediary, terminating TCP connection and re-initiating on the requesters behalf. Their most popular use is for Web Filtering as the server can inspect and if necessary replace or block certain content.
