---
title: "Worklog Tuần 5"
date: 2026-06-08
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu AWS CLI: cài đặt, cấu hình, và cách thao tác với các dịch vụ AWS phổ biến (S3, SNS, IAM, VPC, EC2) qua command line.
* Tìm hiểu Amazon DynamoDB: khái niệm cơ bản, cách thao tác dữ liệu qua Console, CloudShell và AWS SDK (Python).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                              |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------ |
| 2   | - Tìm hiểu tổng quan AWS CLI, các bước chuẩn bị <br> - **Thực hành:** Cài đặt AWS CLI, cấu hình profile & access key                                                                             | 08/06/2026   | 08/06/2026      | <https://000011.awsstudygroup.com/1-introduce/>              |
| 3   | - **Thực hành:** Xem thông tin tài nguyên qua CLI <br> - **Thực hành:** Thao tác với Amazon S3, Amazon SNS và IAM bằng AWS CLI                                                                  | 09/06/2026   | 09/06/2026      | <https://000011.awsstudygroup.com/4-infras/>                 |
| 4   | - **Thực hành:** Tạo VPC & Internet Gateway bằng CLI <br> - **Thực hành:** Tạo EC2 instance bằng CLI <br> - Troubleshooting & dọn dẹp tài nguyên đã tạo                                        | 10/06/2026   | 10/06/2026      | <https://000011.awsstudygroup.com/8-network/>                |
| 5   | - Tìm hiểu tổng quan Amazon DynamoDB: <br>&emsp; + Core components <br>&emsp; + Primary Key & Secondary Index <br>&emsp; + Naming rules & Data types <br>&emsp; + Read Consistency, Capacity Mode | 11/06/2026   | 11/06/2026      | <https://000060.awsstudygroup.com/1-introduce/>              |
| 6   | - **Thực hành:** Thao tác DynamoDB qua Management Console <br>&emsp; + Tạo table, ghi/đọc/cập nhật/truy vấn dữ liệu <br>&emsp; + Tạo & truy vấn Global Secondary Index                          | 12/06/2026   | 12/06/2026      | <https://000060.awsstudygroup.com/2-prerequiste/>            |
| 7   | - **Thực hành:** Thao tác DynamoDB bằng AWS SDK (Python) <br>&emsp; + Tạo table, CRUD dữ liệu, load sample data, query/scan <br> - Dọn dẹp toàn bộ tài nguyên đã tạo trong tuần                | 13/06/2026   | 13/06/2026      | <https://000060.awsstudygroup.com/3-gettingstartedwithawssdk/> |

### Kết quả dự kiến đạt được tuần 5:

* Hiểu AWS CLI là gì, cách cài đặt và cấu hình (Access Key, Secret Key, Region, output format, profiles).
* Tự tạo được VPC, Internet Gateway và EC2 instance bằng AWS CLI mà không cần dùng Console.
* Hiểu Amazon DynamoDB là gì, nắm được các thành phần cốt lõi: Primary Key, Secondary Index, quy tắc đặt tên, kiểu dữ liệu, Read Consistency và Read/Write Capacity Mode.
* Thực hành thành thạo các thao tác CRUD (tạo, đọc, ghi, cập nhật, truy vấn) trên DynamoDB qua cả Management Console và CloudShell.
* Biết cách tạo và truy vấn Global Secondary Index để mở rộng khả năng truy vấn dữ liệu.
* Biết cách dọn dẹp tài nguyên sau khi thực hành để tránh phát sinh chi phí ngoài ý muốn.
