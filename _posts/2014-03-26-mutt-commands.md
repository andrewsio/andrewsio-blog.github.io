---
title: "Useful Mutt Commands"
date: "2014-03-26"
layout: post
categories: blog
tags: linux
---

As some of you may or may not know I'm a big fan of the Mutt email client. It's an entirely CLI-based Linux client that is crazy powerful and very, very geeky. One fantastic feature of Mutt is its integration with GPG, which makes using PGP very simple and painless. Anyway... The thing with Mutt is that it takes some getting used to - I've been using if for about two years and I'm still learning new commands! This blog post will be somewhere that I can keep my useful Mutt commands so I can reference them when I forget, perhaps you'll find it useful too. Force Mutt to decrypt PGP ASCII Armour (legacy encrypted) messages: `ESC P` (Shift-ESC-p)

Change back to the INBOX folder `c` (to enter the change menu), `!` (Shift-1)

Tag all messages that match a pattern (e.g. 'Facebook') `T` (shift-t), then enter your pattern and hit return.

Perform actions on tagged messages (e.g. delete the messages we tagged in the last command) `;` (...then your action) `d` then hit return. `;d` will delete all tagged messages `;s` which will allow you to move the messages to a different IMAP folder, you will be prompted to find the folder you wish to move to.
