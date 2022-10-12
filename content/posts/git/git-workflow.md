---
title: "Cơ chế hoạt động của git 🤟"
date: 2022-10-06T12:13:32+05:30
description: "Bạn có chắc đã hiểu về git ..."
tags: [git_basic]
---

### Git basic.

## 1️⃣ Cơ chế hoạt động của git.

![My imageg](/images/git_flow.jpeg)

🏀 ***Remote repository***:
```
    là repository để chia sẻ giữa nhiều người và được bố trí trên server chuyên dụng 
    như (Github, Bitbucket, Gitlab ...)
```

🏀 ***Local repository***:
```
    là repository bố trí trên máy của bản thân mình, dành cho một người dùng sử dụng.
    Sau khi bạn gõ `git commit` thì các thay đổi sẽ lưu tại đây.
```

🏀 ***Staging Area / Index***:
```
    là nơi lưu trữ các thay đổi trước khi commit. 
    Sau khi bạn gõ `git add` thì các thay đổi sẽ được lưu tại đây.
```

🏀 ***Workspace***:
```
    Là nơi các developer làm việc trực tiếp với files.
```
## 2️⃣ Trạng thái cơ bản của file trong git.

![My imageg](/images/stage_of_files.jpeg)

