---
title: "Serverless là gì?"
date: 2023-10-08
description: "Cơ bản về serverless ?"
tags: [devops]
---

### Serverless là gì ?
`Serverless` là một mô hình phát triển dựa trên đám mây cho phép các nhà phát triển xây dựng và chạy các ứng dụng mà không cần phải quản lý máy chủ.  
Nhà cung cấp đám mây phân bổ tài nguyên máy theo yêu cầu, chăm sóc các máy chủ thay cho khách hàng của họ.

## Ưu điểm
+ `Không cần quản lý máy chủ.`  
    Mô hình này cho phép người dùng không cần quản lý máy chủ, bảo trì hay quản trị phần mềm.
+ `Khả năng mở rộng.`  
    Người dùng sẽ không cần lo lắng về việc mở rộng giải pháp, quy mô nếu nhu cầu sử dụng tăng lên.
+ `Tính sẵn sàng cao.`  
    Mô hình này có khả năng chịu lỗi cao và tính sẵn sàng cao, người dùng không cần lo lắng về quyết định chọn kiến trúc cho ứng dụng.
+ `Tối ưu dung lượng sử dụng.`  
    Người dùng không cần trả chi phí cho thời gian nhàn rỗi nào, nếu ứng dụng không ở trạng thái hoạt động.

## Nhược điểm.
+ `Độ trễ`  
    Các chức năng phức tạp hoặc hoạt động lâu không tốt cho serverless, có thể chờ tới 300s.
+ `Phụ thuộc bên thứ 3`  
    Tất nhiên, vì bạn đang sử dụng dịch vụ bên thứ 3.
+ `Khó debug`
    Vì sử dụng các bên thứ 3, nên các dịch vụ khó có sự thống nhất khi trace logs hoặc tìm hiểu nguyên nhân.