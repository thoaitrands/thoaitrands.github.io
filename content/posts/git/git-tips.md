---
title: "Một số lệnh git bạn cần biết 💯💯"
date: 2022-08-28T12:13:32+05:30
description: "Các câu lệnh nằm lòng của dev"
tags: [git_advanced]
---

### How to undo a Git commit that was not pushed

1. ## Undo commit and keep all files staged (already `git add`)

    ```
    git reset --soft HEAD~;
    ```

2. ## Undo commit and unstage all files (*not include* `git add`)
    ```
    git reset HEAD~;
    ```

3. ## Undo the commit and completely remove all changes
    ```
    git reset --hard HEAD~;
    ```
