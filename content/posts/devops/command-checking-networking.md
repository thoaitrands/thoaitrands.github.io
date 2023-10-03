---
title: "Các câu lệnh cần biết trong network ?"
date: 2022-06-06T12:13:32+05:30
description: "Check your network configuration. Make sure the network in ..."
tags: [network]
---

### --nslookup-- (Name Server Lookup)

1. Tra cứu máy chủ, câu lệnh này cho phép người dùng lấy thông tin từ máy chủ DNS.
    ```
    nslookup <tên miền>
    nslookup <địa chỉ IP>

    ❯ nslookup devopsbasic.info
    Server: 2001:ee0:26::26
    Address: 2001:ee0:26::26#53

    Non-authoritative answer:
    Name: devopsbasic.info
    Address: 185.199.111.153
    ```
2. Bạn muốn kiểm tra xem request của bạn đã qua những đâu
    ```
    traceroute devopsbasic.blog
    ```
