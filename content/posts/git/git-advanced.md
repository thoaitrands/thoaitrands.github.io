---
title: "Advanced Git Tutorials."
date: 2022-05-27T12:13:32+05:30
description: "Git is easy to learn...."
draft: true
tags: [git]
---

If you’re a developer today, odds are you’ve learned Git, the version control system at the heart of modern software workflows. You know the basics — how repositories work, how to create branches and commit changes, and how to merge those changes and pull requests.

But sometime you have some issues with it and you need to know some another git command.

## Git git-cherry-pick

**Issue**  
    If you are working in branch AAA, and your branch have list commits (a1, a2 and a3). It's mean you have 3 commits in your branch. And your boss want to apply the code of commit a2 to master branch, just all code in commit a2 (no more), maybe commit a2 can fix the bug production **Urgent** 😊😊😊😊.   
    ========>>>>>>
**Idea**   
    *What you will do ????*   
        1. Create a new branch HOT-FIX.
        2. Copy all code from commit a2 in branch AAA.  
        3. Commit and push.  
        4. Merge branch HOT_FIX to master.  
        5. Boss, I want a raise salary.  