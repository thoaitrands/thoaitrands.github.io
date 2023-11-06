---
title: "Hệ thống files và lưu trữ trong Linux"
date: 2023-11-06T12:13:32+05:30
description: "Giải ngố về hệ thống tệp trong Linux"
tags: [linux]
---

### Linux file system overview
![My imageg](/images/linux_filesystem.png)

### Giải thích cụ thể các folders trong linux

`bin`: Viết tắt của binary, các tệp nhị phân của hệ thống, các tệp thực thi và công cụ hầu như được tìm thấy ở đây.

`boot`: Tất cả các tệp mà hệ thống cần dùng để khởi động, làm thế nào để khởi động.

`vim`: Bạn có thể tìm thấy thông tin thiết bị tại đây.

`etc`: Đây là thư mục quan trọng nhất trong hệ thống Linux, vì đây là nơi chưa phần lớn các tệp cấu hình.

`home`: Là nơi sẽ tìm được các tệp và thư mục của người dùng.

`lib`: Là nơi chứa các thư viện chung để dùng thực thi các lệnh trong thư mục `bin`

`media`: Là nơi tìm thấy các thiết bị di động.

`opt`: Gối phần mền tùy chọn (Optional software packages).

`proc`: Thông tin về kernel và thông tin về process.

`root`: Thư mục home của root (cần permission root để truy cập thư mục này).

`run`:  Placeholder cho trạng thái ứng dụng.

`sbin`: Tương tự như `bin` nhưng chứa các công cụ nâng cao hơn, dành cho những user có đặc quyền nâng cao trong hệ thống.

`tmp`: Chứa các thư mục tạm.

`user`: Chứa các gói phần mềm được cài đặt bởi user.

`var`: Chứa các files logs mà thư mục `bin` sau khi thực thi.




