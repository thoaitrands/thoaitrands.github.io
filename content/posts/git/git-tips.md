---
title: "Some Git command You NEED 💯💯"
date: 2022-08-28T12:13:32+05:30
description: "The commands You need when you use GIT"
tags: [git_advanced]
---

### Git Advanced 🥺🥺🥺 (for me).

## 1️⃣ git reset

    git reset --hard commit_ID

    - Quay lại một điểm commit nào đó
    - Xoá history commit trước đó.
    - `git push -f `

🔴 usecase: Nếu git add 5 files (chưa commit), mình muốn revert lại 5 files added —> `git reset`

🌼 `Git reset <commit_id>`: Di chuyển con trỏ `HEAD` về vị trí commmit reset.  
    🌱 **Giữ nguyên tất cả các thay đổi của file**, nhưng loại bỏ các thay đổi khỏi `stage`.

🌼 `Git reset --soft <commit_id>` : Lệnh này chỉ di chuyển `HEAD` về vị trí commit.  
    🌱 Trạng thái của `stage` và tất cả sự thay đổi của file sẽ được giữ nguyên.

🌼 `Git reset --hard <commit_id>` : Di chuyển con trỏ HEAD về vị trí commmit reset  
    🌱  Loại bỏ tất cả sự thay đổi của file.

------------------------------------
***********************************
## 2️⃣ git rebase

Gộp các commits lại với nhau, trong trường hợp branch của bạn có quá nhiều commits không cần thiết, hoặc để gọn lại số lượng commits.

1. Check log `git log --oneline` ---> output: 

    ```
        4fb586a (HEAD -> re_branch_1, origin/re_branch_1) This is commit C3   
        9d18fc1 This is commit C2   
        da7f779 This is commit C1   
        6183559 add new file   
        de65104 (origin/main, main) add pre-commit   
        6877365 Init project
    ````
2. Thực hiện lệnh gộp commit. (gộp 3 commits)
    ```
        git rebase -i HEAD~N   
        N: Số lượng commits cần gộp. 
    ```
    ```
        pick da7f779 This is commit C1  
        pick 9d18fc1 This is commit C2  
        pick 4fb586a This is commit C3  
    ```
    chỉ giữ `pick` đầu tiên, còn lại chuyển sang `s` thay vì `pick` 👉👉
    ```
        pick da7f779 This is commit C1  
        s 9d18fc1 This is commit C2  
        s 4fb586a This is commit C3  
    ```

3. Thay đổi message commit gộp.
4. Kiểm tra logs để đảm bảo là mình đã gộp commit dưới local `git log --oneline`
5. `git push -f`

[Chi tiết git rebase](https://blog.haposoft.com/series-git-nang-cao-phan-iii-git-rebase/#:~:text=Git%20rebase%20l%C3%A0%20m%E1%BB%99t%20ch%E1%BB%A9c,c%C3%A1c%20commit%20c%C6%A1%20s%E1%BB%9F%20m%E1%BB%9Bi.).



## 2️⃣ git rebase


