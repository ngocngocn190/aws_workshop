---
title: "Worklog Tuần 7"
date: 2026-06-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Mục tiêu tuần 7:

* Tìm hiểu Amazon Route 53 và dịch vụ Route 53 Resolver.
* Thực hành xây dựng hệ thống Hybrid DNS, tích hợp DNS on-premise (Microsoft AD) với dịch vụ DNS của AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                    |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------------- |
| 2   | - Tìm hiểu tổng quan về Route 53, Route 53 Resolver và kiến trúc Hybrid DNS <br>&emsp; + Outbound Endpoint <br>&emsp; + Inbound Endpoint <br>&emsp; + Resolver Rules | 22/06/2026   | 22/06/2026      | <https://000010.awsstudygroup.com/vi/1-introduce/>                  |
| 3   | - **Thực hành:** Tạo Key Pair <br> - **Thực hành:** Khởi tạo CloudFormation Template để dựng hạ tầng mẫu                                                     | 23/06/2026   | 23/06/2026      | <https://000010.awsstudygroup.com/vi/2-prerequiste/>                |
| 4   | - **Thực hành:** Cấu hình Security Group <br> - **Thực hành:** Kết nối đến RDGW (Remote Desktop Gateway)                                                     | 24/06/2026   | 24/06/2026      | <https://000010.awsstudygroup.com/vi/3-connecttordgw/>               |
| 5   | - **Thực hành:** Triển khai Microsoft Active Directory                                                                                                        | 25/06/2026   | 25/06/2026      | <https://000010.awsstudygroup.com/vi/4-setupad/>                    |
| 6   | - **Thực hành:** Thiết lập DNS Hybrid <br>&emsp; + Tạo Route 53 Outbound Endpoint <br>&emsp; + Tạo Route 53 Resolver Rules <br>&emsp; + Tạo Route 53 Inbound Endpoints | 26/06/2026   | 26/06/2026      | <https://000010.awsstudygroup.com/vi/5-setuphyriddns/>              |
| 7   | - **Thực hành:** Thử nghiệm kết quả phân giải DNS hai chiều <br> - Dọn dẹp toàn bộ tài nguyên đã tạo trong tuần                                              | 27/06/2026   | 27/06/2026      | <https://000010.awsstudygroup.com/vi/6-cleanup/>                    |

### Kết quả dự kiến đạt được tuần 7:

* Hiểu Amazon Route 53 là gì và vai trò của Route 53 Resolver trong việc phân giải tên miền giữa on-premise và AWS.
* Nắm được 3 thành phần cốt lõi của kiến trúc Hybrid DNS: Outbound Endpoint, Inbound Endpoint và Resolver Rules.
* Tự dựng được hạ tầng mẫu bằng CloudFormation Template và cấu hình Security Group phù hợp.
* Kết nối được đến RDGW và triển khai thành công Microsoft Active Directory trên AWS.
* Thiết lập hoàn chỉnh hệ thống DNS hybrid, cho phép phân giải tên miền hai chiều giữa hệ thống on-premise và AWS.
* Kiểm tra và xác minh được kết quả phân giải DNS sau khi cấu hình.
* Biết cách dọn dẹp tài nguyên sau khi thực hành để tránh phát sinh chi phí ngoài ý muốn.
* ...