---
title: "Worklog Tuần 4"
date: 2025-06-08
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Nội dung dưới đây là kế hoạch dự kiến, chỉ mang tính tham khảo, vui lòng **không sao chép nguyên văn** cho báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 4:

* Tìm hiểu Amazon RDS: cách triển khai cơ sở dữ liệu quan hệ được quản lý, kết nối với EC2, backup & restore.
* Tìm hiểu Amazon CloudWatch: giám sát metrics, logs, thiết lập cảnh báo và dashboard cho tài nguyên AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                          |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------ |
| 2   | - Tìm hiểu tổng quan Amazon RDS: khái niệm, các DB engine hỗ trợ, khi nào nên dùng RDS <br> - **Thực hành:** Chuẩn bị VPC, EC2 Security Group, RDS Security Group, DB Subnet Group                | 08/06/2025   | 08/06/2025       | <https://000005.awsstudygroup.com/vi/1-introduce/>          |
| 3   | - **Thực hành:** Tạo EC2 instance <br> - **Thực hành:** Tạo RDS database instance                                                                                                                    | 09/06/2025    | 09/06/2025      | <https://000005.awsstudygroup.com/vi/3-create-ec2/>          |
| 4   | - **Thực hành:** Triển khai ứng dụng kết nối EC2 với RDS <br> - **Thực hành:** Backup và restore RDS <br> - Dọn dẹp tài nguyên RDS đã tạo                                                            | 10/06/2025    | 10/06/2025       | <https://000005.awsstudygroup.com/vi/5-deploy-app/>          |
| 5   | - Tìm hiểu tổng quan Amazon CloudWatch <br> - **Thực hành:** Các bước chuẩn bị <br> - Tìm hiểu CloudWatch Metric: xem metrics, search expression, math expression, dynamic labels                  | 11/06/2025    | 11/06/2025       | <https://000008.awsstudygroup.com/vi/3-cloud-watch-metric/>  |
| 6   | - Tìm hiểu CloudWatch Logs: Logs, Logs Insights, Metric Filter                                                                                                                                        | 12/06/2025    | 12/06/2025       | <https://000008.awsstudygroup.com/vi/4-cloud-watch-logs/>    |
| 7   | - Tìm hiểu CloudWatch Alarms và Dashboards <br> - Dọn dẹp toàn bộ tài nguyên CloudWatch đã tạo trong tuần                                                                                            | 13/06/2025    | 13/06/2025       | <https://000008.awsstudygroup.com/vi/5-cloud-watch-alarm/>   |

### Kết quả dự kiến đạt được tuần 4:

* Hiểu Amazon RDS là gì, các DB engine được hỗ trợ (Aurora, MySQL, MariaDB, Oracle, SQL Server, PostgreSQL) và khi nào nên chọn RDS thay vì tự triển khai database trên EC2.
* Tự chuẩn bị được hạ tầng mạng (VPC, Security Group, DB Subnet Group) cho một RDS instance.
* Tạo được EC2 instance và RDS database instance, triển khai ứng dụng kết nối giữa hai thành phần này.
* Biết cách thực hiện backup/restore cho RDS database.
* Hiểu Amazon CloudWatch là gì và vai trò trong việc giám sát tài nguyên, ứng dụng trên AWS.
* Biết cách xem và thao tác với CloudWatch Metrics: tìm kiếm, tính toán, tạo dynamic label.
* Biết cách sử dụng CloudWatch Logs và Logs Insights để tra cứu, phân tích log; tạo Metric Filter từ log.
* Thiết lập được CloudWatch Alarms để cảnh báo khi có bất thường, và dựng Dashboard để theo dõi trực quan.
* Biết cách dọn dẹp tài nguyên sau khi thực hành để tránh phát sinh chi phí ngoài ý muốn.
  