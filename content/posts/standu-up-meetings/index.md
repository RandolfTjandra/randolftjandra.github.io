---
title: "Stand up Meetings"
date: 2024-04-04T22:27:41-07:00
draft: false 
summary: "That feeling when you take a Zoom call at the office"
tags: ["software_development"]
---

I think we can agree that time is valuable for everyone. The more time we create, the
more development work can be done. Engineering teams typically have a long laundry list
of tasks that they want to see completed; work is never ending. To that end their time
is critical. It's in the entire organization's best interest to allow them more time to
do more work. When they're in meetings, they're not doing development work.

I understand meetings are important; I'm not saying we should never have meetings again.
We're able to work together to resolve issues and misunderstandings quickly. We plan
work together and we learn from our mistakes. It's when we take on massive initiatives
that could never be accomplished by any of us individually. It's an awesome opportunity
for everyone to grow together. I just don't think it's always the best use
of our time. Take stand up meetings for example.

To my understanding, the purpose of a stand up meeting is to update all of your peers,
direct managers, and stakeholders on what every developer on a team is working on. These
stakeholders then take this information and use it to plan the team's work, update
external stakeholders so they can plan their team's work, and re-asses timelines. Why
then is it important that everyone be at this one meeting same time to give a verbal
update that everyone is either not going to pay attention to, or not remember as soon
as the meeting is over.

Here's the thing about these meetings: they're always at an awkward time. It's supposed
to be a time that's convenient for everyone. Typically this means it should be when
everyone is awake and available. In a world where remote work and inter-time zone teams
are becoming more common, scheduling this one daily 15-20 minute meeting becomes
increasingly awkward. You could do say 11am PST, still in the morning but not early
enough that the night owls aren't still asleep, but this becomes annoying for people
on the east coast, who now have stand up at 2pm? Their day is practically over.
For transparancy I worked on JST, Japan time, which meant that stand up meetings for me
would typically be at 3am. Obviously I never went.

I think a productive solution would be to asynchronously collect daily updates from
everyone on the team by text. On this team I had set up a Slack reminder that pinged
the team for an update every day at the same time. I expected every developer who was
working that day to reply to the thread with their updates. What you get with this is a
tangible record from every day, which is recorded with timestamps, about what everyone
is doing on a given day. If necessary you can look back in time and see what developers
said they were doing so you can evaluate why your team velocity is going the way it is.
You never have to worry about people missing this meeting and therefore losing what
they would have said. Objectively, this is the best way to get daily information across
the team without wasting everyone's time. In fact I know that I can't be the only one
that thinks this way because there are companies out there that offer this as a paid
service.[^1]

We also have to consider the cost of context switching into meetings. A meeting is never
just the duration of that meeting. It also costs the time it takes to disengage from
the work you might be doing at the time leading up to the meeting, then the time
it takes to get back into the work after.

Let's go through a hypothetical stand up meeting, let's say you have 12 people on your
team; 8 software engineers, 1 engineering manager, 1 product manager, 1 QA engineer,
1 devops engineer. People start to populate the stand up meeting space or Zoom meeting
and they spend the first 3-5 minutes talking about their day, their weekend, or so on.
Every person spends 1 or 2 minutes talking about what they ended up doing the day before,
and what they plan on doing today. Every time the manager notices that a software
engineer has run into a road bump they ask what they need to get unblocked; this
conversation takes an additional 1-2 minutes (until someone tells them to continue the
conversation offline). A lot of the time, with a team this size, not everyone's work
is going to be relevant to everyone else's. You end up with a meeting that lasts
longer than it has to. If you consider a half hour stand up for 12 people, that's
6 hours of working time team that could have spent producing value in other ways.

All I'm trying to say is let's consider the time cost meetings, understand what exactly
we're trying to get out of them, then decide if it's really the right use of everyone's
time.

Thanks.

[^1]: Check out [Range](https://www.range.co/) for example
