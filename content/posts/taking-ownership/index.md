---
title: "Taking Ownership"
date: 2024-03-31T19:49:23-07:00
draft: false
summary: "Insider exposes what product owners don't want you to know!"
tags: ["software_development"]
---

I think the biggest shift in the way I was thinking about software development was when I started being asked, 
"How do you know this works?". All the way up until then you and I might have asked the answered the same way,
"I tested it. QA tested it, both in development and in production. It has to be working". While I think this is
totallly valid on the surface, there's a larger, more obvious picture that we should be looking at: "Yes but what
effect is any of your work making?".

Do you know how your product is doing? How is performing? When working with real production software these the
questions you have to start asking yourself. At Crunchyroll I worked on the payments team. That meant that my
team and I were responsible for all the subscription money that came through the service. How do we know that
any of our changes were generating any additional revenue or god forbid, losing the company revenue? Of course
it's probably some manager's job to know that, they could certainly generate revenue reports from
our payment processors, but who's to say that there aren't descrepancies between what they report and we
should be seeing? What if there's a service outage? These are the times it becomes the developers' responsiblity to be 
able to answer these questions and in fact, be proactive about monitoring these
results.

The great thing about working on live products is that it's pretty easy to
monitor for irregularities. I had set up logs for our payment service for
several key events, the most hotly observed ones were: `Free Trial Checkout
Succeeded` and `Subscription Checkout succeeded`. Just from these two event logs
I could have a log aggregator like Sumo Logic[^1] parse and graph them for me so I
could create dashboards that showed metrics that represented all the successful
checkouts on the site through our services over the past week.

When observing this data you'll notice that, "ok the checkouts are cylic. People
just aren't furiously paying for anime in the middle of the night". From there
we can generate additional charts that show things like, how does this week's
checkouts compare to the last. If this week is consistently higher, that's good
news, something right is going with the product. We potentially put something
out that we should be proud of as team. Your change, or project, can directly be
correlated empirically with the continued success of your service; own it! If it's 
not, then let's have a conversation about it. If we can pin it to a specific 
deployment, we should go back and look at its content and see if we can resolve
any unwanted causation. I found that there was so much power in this
information. We can also create charts that show when checkouts deviate negatively from 
standard deviation, and most importantly we can create alerts on these. A really
important weapon we possess to prevent further damage to the product.

When I started building out these dashboards and alerts, the way I approached feature 
development started to revolve around these concepts. I would make sure that the
tasks that I specc'd out would contain requirements that asked the developer
that they implement some way to monitor the outcome of their changes and call
them out if it was missing. It may not seem like a big deal for those of you
that already think about development like this, but to me there's a big
difference in solely thinking about how to solve some engineering problem, and
how to think like a product owner that cares about their service results

[^1]:  Unfortunately I can't show you any of these charts as examples [Sumo Logic](https://www.sumologic.com/)
