---
title: A review of Web Operations by John Allspaw and Jesse Robbins
date: "2010-07-03"
url: /blog/2010/07/03/a-review-of-web-operations-by-john-allspaw-and-jesse-robbins/
categories:
  - Databases
  - Operations
  - Reviews
---
[Web Operations]({{< amz 1449377440 >}}). By John Allspaw and Jesse Robbins, O'Reilly 2010, with a chapter by myself. (Here's [a link to the publisher's site](http://oreilly.com/catalog/0636920000136)).

[![Web Operations](/media/book-covers/web-operations.jpg# 3dbook)]({{< amz 1449377440 >}})

I wrote a chapter for this book, and it's now on shelves in bookstores near you. I got my dead-tree copy today and read everyone else's contributions to it. It's a good book. A group effort such as this one is necessarily going to have some differences in style and even overlapping content, but overall it works very well. It includes chapters from some really smart people, some of whom I was not previously familiar with. John and Jesse obviously have good connections. A lot of the folks are from Flickr.

Here are the highlights in my opinion.

*   Theo Schlossnagle, who has a place on my list of [essential books](/essential-books/), opens things with an overview of what web operations really is, and why it's hard. Don't skip this. Theo's introduction is concise and thoughtful.
*   Eric Ries discusses the benefits of continuous deployment. He is right on the money. Right out of college I spent 3 years as a developer at a company with very little engineering discipline, and then left for another company built by a small ace team practicing extreme programming. Eric nails the benefits of continuous deployment---he really gets it. I hadn't heard of Eric before, but now I've subscribed to [his blog](http://www.startuplessonslearned.com/).
*   John Allspaw (whose book on capacity planning is also on my list of essentials) and Richard Cook discuss how complex systems fail. This chapter appeared in part as a [whitepaper and blog post on John's blog](http://www.kitchensoap.com/2009/11/12/how-complex-systems-fail-a-webops-perspective/), and is expanded in this book. I have spent a lot of time examining failures for clients, and as VP of Consulting, also a lot of time examining Percona's own mistakes. I fully agree with the conclusions in this chapter. A few key points: there is never a single root cause; our desire to find one blinds us and keeps us from learning; *true* failures are inherently unpredictable and happen only when a series of things fails; avoiding failure requires experience with failure. This echoes another book I've read recently, [The Black Swan]({{< amz 1400063515 >}}).
*   [Brian Moon's](http://brian.moonspot.net/) chapter on unexpected traffic spikes. If you get a chance to hear Brian speak, take it. He's an engaging guy with interesting and relevant stories to tell. Stories are always a better experience than bullet points.
*   Jake Loomis's chapter on postmortems. My own research into prevention of emergencies agrees almost perfectly with his list of things to do on page 225. Read this chapter carefully! Now, knowing how to put this into action is hard---very hard---but at least you'll have a place to start. The worst compliment I ever got after fixing a system that'd run out of hard drive space (due to utter lack of basic monitoring) was that I'd "saved the day." Baloney. Postmortems can be a great way to learn your infrastructure's weaknesses and prevent emergencies in the future. I'm fully confident that this particular client will again deploy new servers without adding them into Nagios, and the results will be predictable.
*   Naturally, my chapter about choosing a relational database architecture for web applications (skewed towards MySQL). There is a chapter on NoSQL databases by Eric Florenzano as well, but it is more introductionary-level.

What wasn't so good? I didn't get a lot of value out of John's interview with Heather Champ, on community management and web operations. I did not think the interview format worked well in a book full of essays. But that might just be me. Also, a couple of places in two or three chapters felt a bit rant-ish without a lot of clear actionable advice; I think readers won't get so much out of this.

Overall, though, this is a great book, badly needed, on a topic that is simply not yet recognized for its true importance. As Theo writes, we're seeing the emergence of web operations as a very large profession; it's one whose definition is not yet formalized or agreed-upon, but that'll change. It's too important not to. Jesse's introduction repeats this sentiment: the world now relies on the web, and so the world relies also on the engineers who make it run. Web operations is work that matters.


