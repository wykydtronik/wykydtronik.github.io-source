---
title: More Independent Learning
date: 2017-03-09 20:23:59
tags:
---
A colleague recommended I start using the Enki app for daily practice my knowledge on JavaScript and Git. Apparently I already have an account! I'm pretty sure I created the account back when the app was in beta. Right off the bat, I couldn't recall a lot of this with Linux CLI and learned a few things I haven't even seen in JavaScript books.

Another thing I've taken a liking for is listening to JavaScript or programming related talks while at the gym. I know I'm falling far behind on my typical YouTube vlogs, but meh, I'm really trying to go all out with JavaScript.

I've breezed through Week 4 of the Coursera JavaScript courses and I'm ready to start working on this weeks assignments. I really need to crank these out before Friday night. I don't want to get distracted with the weekend and forget the assignments are due on the 12th!

The JavaScript book I'm reading through is very dry and the examples are garbage. I guess spending a lot of time trying to figure out how to make the examples work in a browser is what they want you to do even though they don't really say to try it... they just give you lines of code that doesn't function alone... like having to build a function or knowing advanced HTML5 and CSS3... Meh, I'm probably going to be pissed once I get to the jQuery chapter if they're going to assume I know everything. #neckbeards

Outside of my daily JS exercises, I spent the day deploying garbage code. Apparently this premium WordPress theme my company bought queries WP admin-ajax.php with a massive string every time an individual visits the page. Multiple that by 2 (widget appears twice) and 465 individual ip's during a slashdot - YEAH. It took a long time to figure out wtf was going on! First, 2 pointless sql queries were running. Axed them, database stabilized. After an hour, httpd was on fire with over 100 spawned instances. THEY WERE ALL BECAUSE OF THE AJAX QUERIES! SHIT CODE!

The bright side of this? That silver lining? I learned how to properly SSH into an AWS RDS and regulate, I also learned a few little tricks for quickly gaining access to the error_log and access_log on AWS EC2's (standard AMI). Well well well, would you look at that? Full stack DEVOP live in the mix. Seriously though, I need to keep cranking away at JavaScript. They don't pay me enough for something I could probably get triple the salary for...
