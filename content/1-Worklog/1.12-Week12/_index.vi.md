---
title: "Worklog Tuần 12"
date: 2026-07-27
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---



### Mục tiêu tuần 12:

* Kiểm thử toàn diện dự án AI AWS Advisor, hoàn thiện tài liệu còn lại.
* Dọn dẹp tài nguyên AWS đã sử dụng trong suốt quá trình làm dự án và chuẩn bị báo cáo/demo cuối kỳ.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                |
| --- | -------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------------------------- |
| 2   | - **Thực hành:** Chạy các test case quan trọng (tạo project, trigger sync, phát hiện S3 public, IAM AdministratorAccess...)        | 27/07/2026   | 27/07/2026      |      |
| 3   | - **Thực hành:** Kiểm tra logs của Collector Lambda và API Lambda qua CloudWatch <br> - Viết docs/06-reflection.md                | 28/07/2026   | 28/07/2026      |      |
| 4   | - **Thực hành:** Deploy end-to-end bản hoàn chỉnh, kiểm tra Dashboard hiển thị đúng dữ liệu thật                                  | 29/07/2026   | 29/07/2026      |      |
| 5   | - Rà soát lại phần bảo mật: kiểm tra IAM Role tuân thủ least privilege, không hardcode Access Key, review audit trail qua CloudWatch | 30/07/2026   | 30/07/2026      |      |
| 6   | - Chuẩn bị nội dung demo/báo cáo cuối kỳ cho dự án AI AWS Advisor                                                                  | 31/07/2026   | 31/07/2026      |      |
| 7   | - **Thực hành:** Viết docs/05-cleanup.md <br> - Dọn dẹp toàn bộ tài nguyên AWS đã tạo trong suốt dự án (SAM stack, DynamoDB, SNS, S3, Log Groups) | 01/08/2026   | 01/08/2026      |      |

### Kết quả dự kiến đạt được tuần 12:

* Toàn bộ test case quan trọng đều pass, xác nhận hệ thống hoạt động đúng như thiết kế.
* Biết cách tra cứu log qua CloudWatch để debug khi cần, và có bài viết reflection tổng kết quá trình làm dự án.
* Có bản deploy end-to-end hoàn chỉnh, dashboard hiển thị dữ liệu thật từ tài khoản AWS sandbox.
* Xác nhận hệ thống tuân thủ các nguyên tắc bảo mật cơ bản: least privilege, không lưu access key, có audit trail.
* Chuẩn bị xong nội dung để demo/báo cáo dự án trước nhóm hoặc giảng viên hướng dẫn.
* Dọn dẹp thành công toàn bộ tài nguyên AWS đã sử dụng, tránh phát sinh chi phí ngoài ý muốn sau khi kết thúc dự án.
* ...