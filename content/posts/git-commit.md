---
title: "Git Commit"
tags: ['git']
date: 2024-03-31T13:51:28-07:00
draft: false
summary: 'Implement this and that, and this and that, and this and that, and this and that...'
---

I come from experience where the work we did was documented on Jira. The task description, requirements, and QA procedure were all recorded there. This is useful as non developer stakeholders usually do not have access to a project's git commit history. Besides, who wants to navigate through git just to see what work is being done?

I like to think that commit messages should be as succinct as possible. It should only describe the content of the work. Additional information such as how to test this work, detailed changes, should all go into your project management software issues or other documentation. When a commit message has to spend multiple sentences describing its content, that says a lot about your team's approach to planning work. Your commit probably would benefit from being split up.

With smaller commits, pull requests will be quicker because they're focused on a singular task. QA becomes more straightforward because you're narrowing down the area of concern. You simplify the hypothetical process of reverting your changes in the rare case something goes awry. Overall you improve the health of your project's commit history as it becomes more iterative and readable, and you reduce the time it takes for your work to reach production because there are fewer barriers to get through.

Imagine the opposite scenario where you and your team plan out an entire project into a single commit, waterfall style. As you develop the project you also spot areas where code can be improved so you start doing refactors as well. Over time your project branch drifts against main, which will potentially make it difficult to merge your work later.

The refactors could have happened separately and merged sooner. That's something all contributors would benefit from. The fact that these irrelevant changes came up during your work could be indication that you've been on this branch for too long, going back to what I said about being able to succinctly describe your work in your commit message.

I'll talk about how I think tasks should be designed in another post.

## Commit Message

Below is my .gitmessage file. The first line is reserved for a single sentence describing what the contents of the commit. Issue refers to the project issue that the commit is addressing. Reviewer is a list of names of people who reviewed the code. Any additional context that's necessary should come after.

I don't think the reviewer line is totally necessary if you'd prefer to just refer to the pull request for this information.

My preference is for commit messages to be in imperative verb form.

> Eg. Fix issue where transactions are attributed to the wrong user

```


Issue: none
Reviewer: pending
```

This is my prepare-commit-msg file (chmod +x this file).

```
#!/bin/sh
#
# Assumes branches follow the format `draft-[project]-[ticket_number]`
# Also assumes you're using the standard gitmessage
#
# Converts branch name into Issue ticket
sed -i.bak "s/Issue: none/Issue: $(git branch | grep '*' | sed -E 's/\* //;s/([a-zA-Z]+-[0-9]+).*/\1/' | tr '[:lower:]' '[:upper:]')/" "$1"
```

My workflow is: I go to my project management software, get my current task identifier (which follows the format eg. project-123), create a new branch with that as its name, then have my commits automatically tag the commit message with that issue identifier.

eg.
When my branch name is work-435, prepare-commit-msg formats my commit message to:

```


Issue: WORK-435
Reviewer: none
```

## Git hooks

An additional thing I have set up are the follow lines in my .gitconfig.

```
[core]
  hooksPath = ~/.git-hooks
```

.git-hooks/ contains my prepare-commit-msg file.
When I run git init in any of my git repos, it'll run my hooks if present before it looks for a local copy.
