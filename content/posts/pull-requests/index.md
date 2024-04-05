---
title: "Pull Requests"
tags: ['git']
date: 2024-04-04T23:23:29-07:00
draft: false
summary: 'pull request virtue signalling'
---

I'd like to layout the personal rules I have for creating pull requests. (Doesn't apply
when I'm working on my own public repos!) I like to think of pull requests as 
presentations. You're presenting your work to your team, it should paint a cohesive
picture.

1. Add additional context to your issue tracker and documentation (Jira, Clickup, Linear, GH Issues).
    - This information should include how to test your work, additional changes you made
    that may have deviated from the original design.
1. Prepare your branch. Ideally you only have a single commit in your branch at the 
time of review. Just rebase or merge squash your commits together.
    - The only exception to this would be if your pull request is particularly complicated
    and separating your work into commits presents a easier story for reviewers to follow.
1. Link your PR to your issue tracking software 
1. That's pretty much it

When you merge your work into main, squash it and follow your project or organization's
message template. You can see my other post "Git Commit" to see my take.

