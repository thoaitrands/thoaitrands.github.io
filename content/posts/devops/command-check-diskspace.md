---
title: "Cách kiểm tra dung lượng đĩa trong linux"
date: 2022-11-05T12:13:32+05:30
description: "Hướng dẫn cách để kiểm tra các folders đã sử dụng bao nhiêu dung lượng ..."
tags: [linux]
---

### --df-- (disk filesystem)

Dùng để lấy toàn bộ thông tin về lượng ổ cứng khả dụng và lượng ổ cứng đã dùng của các files hệ thống trên linux.

### --du-- (disk usage)

Dùng để thể hiện dung lượng ổ đĩa được sử dụng bởi các thư mục và files

```
    du <option> <path|file>
    du <option> <path1> <path2> <path3>
```

Mặc định kích thước hiển thị là kilobytes, tuy nhiên có thể thay đổi sang đơn vị đo khác.
```
    du -BM ~/.bashrc
```

Có thể lấy kính thước thực tế của file đó.
```
    du -h --apparent-size ~/.bashrc
```

Kiểm tra dung lượng đĩa đã sử dụng cho thư mục:
```
    du -shc thoaitrands.github.io git_advanced
        12M     thoaitrands.github.io
        60M     git_advanced
        71M     total
```
`c`: total  
`h`: human readable  
`s`: summarize  

Kiểm tra dung lượng đĩa đã sử dụng cho images và text.
```
    find / -name *.png 2> /dev/null | xargs du -ch
    find / -name *.txt 2> /dev/null | xargs du -ch
```