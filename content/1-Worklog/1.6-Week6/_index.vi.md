---
title: "Worklog Tuần 6"
date: 2026-06-15
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Nội dung dưới đây là kế hoạch dự kiến, chỉ mang tính tham khảo, vui lòng **không sao chép nguyên văn** cho báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 6:

* Tìm hiểu Grafana: công cụ trực quan hóa và phân tích mã nguồn mở, dùng để giám sát tài nguyên và ứng dụng.
* Thực hành triển khai Grafana trên EC2 instance và cấu hình giám sát tài nguyên AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Tìm hiểu tổng quan về Grafana và vai trò trong giám sát hệ thống <br> - **Thực hành:** Chuẩn bị VPC & Subnet, tạo Security Group                                        | 15/06/2026   | 15/06/2026      | <https://000029.awsstudygroup.com/2-prerequiste/>                     |
| 3   | - **Thực hành:** Khởi tạo EC2 instance <br> - **Thực hành:** Tạo IAM User, tạo IAM Role và gán Role cho EC2                                                                | 16/06/2026   | 16/06/2026      | <https://000029.awsstudygroup.com/2-prerequiste/2.4-createiamuser/>   |
| 4   | - **Thực hành:** Cài đặt Grafana trên EC2 instance (Linux)                                                                                                                    | 17/06/2026   | 17/06/2026      | <https://000029.awsstudygroup.com/3-installgrafana/>                  |
| 5   | - **Thực hành:** Cấu hình data source cho Grafana <br> - Tìm hiểu cách xây dựng dashboard giám sát tài nguyên AWS                                                          | 18/06/2026   | 18/06/2026      | <https://000029.awsstudygroup.com/4-monitoringwithgrafana/>           |
| 6   | - **Thực hành:** Tiếp tục cấu hình panel, biểu đồ giám sát và thử nghiệm alert trên Grafana dashboard                                                                       | 19/06/2026   | 19/06/2026      | <https://000029.awsstudygroup.com/4-monitoringwithgrafana/>           |
| 7   | - Rà soát lại toàn bộ quá trình triển khai <br> - Dọn dẹp tài nguyên (EC2, IAM User/Role, Security Group, VPC) đã tạo trong tuần                                            | 20/06/2026   | 20/06/2026      | <https://000029.awsstudygroup.com/5-cleanup/>                         |

### Kết quả dự kiến đạt được tuần 6:

* Hiểu Grafana là gì và vai trò của nó trong việc trực quan hóa, phân tích và giám sát tài nguyên/ứng dụng.
* Tự chuẩn bị được hạ tầng cần thiết (VPC, Subnet, Security Group) để triển khai Grafana trên AWS.
* Tạo được EC2 instance, IAM User và IAM Role, biết cách gán Role phù hợp cho instance để Grafana có quyền truy vấn dữ liệu giám sát.
* Cài đặt thành công Grafana trên EC2 instance chạy Linux.
* Cấu hình được data source và xây dựng dashboard cơ bản để giám sát tài nguyên AWS bằng Grafana.
* Biết cách dọn dẹp toàn bộ tài nguyên đã tạo sau khi thực hành để tránh phát sinh chi phí ngoài ý muốn.
