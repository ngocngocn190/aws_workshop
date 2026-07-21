---
title: "Worklog Tuần 3"
date: 2025-06-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Nội dung dưới đây là kế hoạch dự kiến, chỉ mang tính tham khảo, vui lòng **không sao chép nguyên văn** cho báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 3:

* Tìm hiểu Amazon EC2: cách khởi tạo, cấu hình instance trên cả Windows và Linux, triển khai ứng dụng thực tế.
* Tìm hiểu Amazon S3: lưu trữ object, static website hosting, tăng tốc bằng CloudFront.
* Thực hành áp dụng IAM để giới hạn quyền sử dụng tài nguyên, kiểm soát chi phí.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                              |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------------------------------------------------------- |
| 2   | - Tìm hiểu tổng quan Amazon EC2 <br> - **Thực hành:** Chuẩn bị VPC & Security Group cho Linux/Windows instance                                                                                              | 01/06/2025    | 01/06/2025      | <https://000004.awsstudygroup.com/vi/1-introduce/>            |
| 3   | - **Thực hành:** Khởi tạo & kết nối Windows instance, Linux instance <br> - Tìm hiểu EC2 cơ bản: <br>&emsp; + Thay đổi cấu hình EC2 <br>&emsp; + Tạo EBS Snapshot <br>&emsp; + Tạo & khởi chạy Custom AMI | 02/06/2025    | 02/06/2025       | <https://000004.awsstudygroup.com/vi/3-launchwindowsinstance/> |
| 4   | - **Thực hành:** Triển khai ứng dụng Node.js (AWS User Management) <br>&emsp; + Trên Linux: LAMP server, phpMyAdmin, Node.js <br>&emsp; + Trên Windows: XAMPP, Node.js <br> - Áp dụng IAM giới hạn quyền sử dụng tài nguyên (region, instance type, EBS...) | 03/06/2025    | 03/06/2025       | <https://000004.awsstudygroup.com/vi/6-awsfcjmanagement-linux/> |
| 5   | - Tìm hiểu tổng quan Amazon S3 <br> - **Thực hành:** Tạo S3 bucket, tải dữ liệu lên <br> - Bật static website hosting                                                                                        | 04/06/2025    | 04/06/2025      | <https://000057.awsstudygroup.com/vi/1-introduce/>            |
| 6   | - **Thực hành:** Cấu hình Block Public Access & public object <br> - Kiểm tra website tĩnh <br> - Tăng tốc website với Amazon CloudFront                                                                    | 05/06/2025    | 05/06/2025       | <https://000057.awsstudygroup.com/vi/7-cloudfront/>            |
| 7   | - **Thực hành:** Bucket Versioning, di chuyển & sao chép object sang region khác <br> - Dọn dẹp toàn bộ tài nguyên EC2 & S3 đã tạo trong tuần                                                                | 06/06/2025    | 06/06/2025      | <https://000057.awsstudygroup.com/vi/8-versioning/>            |

### Kết quả dự kiến đạt được tuần 3:

* Hiểu cách hoạt động và các thành phần cơ bản của Amazon EC2: instance, AMI, EBS, Security Group.
* Tự khởi tạo và kết nối được EC2 instance trên cả Windows Server và Amazon Linux.
* Triển khai thành công một ứng dụng Node.js CRUD đơn giản (AWS User Management) trên cả 2 hệ điều hành.
* Biết cách dùng IAM để giới hạn quyền sử dụng tài nguyên (theo region, loại instance, thời gian...) nhằm kiểm soát chi phí.
* Hiểu Amazon S3 là gì, cách tạo bucket, tải dữ liệu và bật static website hosting.
* Biết cách cấu hình quyền truy cập public một cách an toàn, và tăng tốc website bằng CloudFront.
* Nắm được cách quản lý version của object trong S3 và sao chép dữ liệu giữa các region.
* Biết cách dọn dẹp tài nguyên sau khi thực hành để tránh phát sinh chi phí ngoài ý muốn.
