---
title: "Git LFS là gì trong cuộc đời này ??"
date: 2023-09-13T12:13:32+05:30
draft: true
description: "Lần đầu làm chuyện ấy ..."
tags: [git, git_advanced]
---

## Git merge
    Beta                   `B1` ------------------------> `B2`
                         /            
                        /
    Main: `C1` ---> `C2` ----------> `C3` ---> `C4`
👉👉👉      `C1` --->`C2` --->`B1` --->`C3`---> `C4` --->`B2`

    🐵 Nếu chúng ta merge `Beta` branch vào `main` branch.

    Sau khi merged, thì `commit history` sẽ được sắp xếp dựa vào thời gian của các commits.

    👉 B1 được commit trước C3 và C4
    👉 B2 commit sau C3 và C4
    
    `commit history` sau khi merged sẽ là 👉👉👉 B1 —> C3 —> C4 —>B2

## Git rebase
    Beta                   `B1` ------------------------> `B2`
                         /            
                        /
    Main: `C1` ---> `C2` ----------> `C3` ---> `C4`
👉👉👉     `C1` ---> `C2` --->`C3` --->`C4`---> `B1` --->`B2`

    🐵 Đứng ở branch `beta` để rebase branch `main`:
	  👉 Lấy branch `main` làm cơ sở.
	  👉 Giữ thứ tự các commits của branch `main`, lấy tất cả các commits của branch `beta` đẩy lên đầu branch `main`
    `commit history` sau khi merged sẽ là 👉👉👉 C1 —> C2 —> C3 —>C4 -> B1 ->B2.

Sẽ đem những commits (từng commit) bên nhánh `Beta` và áp dụng lại vào sau commit mới nhất của nhánh `Main`

## Lợi ích:

    👍 Sau khi 1 branch hoàn thành nên rebase main thay vì merge. 
    vì các commits của new branch sẽ không xen kẽ với commits của main —> dễ check history.
