---
title: "Worklog Tuần 8"
date: 2026-06-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---


### Mục tiêu tuần 8:

* Tìm hiểu và lên ý tưởng cho dự án nhóm "AI AWS Advisor" (Cloud Operations Copilot) — nền tảng quản trị hạ tầng AWS thông minh có AI hỗ trợ phân tích.
* Nắm rõ bài toán cần giải quyết, đối tượng sử dụng, tính năng chính và kiến trúc tổng thể trước khi bắt tay vào code.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu           |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------------------- |
| 2   | - Đọc tài liệu tổng quan dự án <br> - Xác định rõ bài toán cần giải quyết (quản trị hạ tầng AWS thủ công tốn thời gian, khó phát hiện rủi ro) | 29/06/2026   | 29/06/2026      |   |
| 3   | - Tìm hiểu đối tượng sử dụng (Cloud Engineer, DevOps, Solution Architect, System Admin, Technical Manager) <br> - Tổng hợp tính năng chính cần có | 30/06/2026   | 30/06/2026      |   |
| 4   | - Tìm hiểu kiến trúc hệ thống tổng thể: luồng dữ liệu từ Resource Collector → DynamoDB → AI Analyze → Dashboard                          | 01/07/2026   | 01/07/2026      |   |
| 5   | - Tìm hiểu công nghệ sử dụng: Backend (Lambda, boto3, SAM), Frontend (React, Tailwind), Infrastructure as Code                           | 02/07/2026   | 02/07/2026      |   |
| 6   | - Tìm hiểu cấu trúc thư mục dự án và Database Schema (4 bảng DynamoDB: projects, resources, insights, alerts)                             | 03/07/2026   | 03/07/2026      |   |
| 7   | - Tìm hiểu API Contract (Projects, Resources, Insights, Chat, Alerts) <br> - Tổng hợp lại toàn bộ ý tưởng, chuẩn bị đề xuất cho nhóm       | 04/07/2026   | 04/07/2026      |   |

### Kết quả dự kiến đạt được tuần 8:

* Hiểu rõ bài toán mà dự án AI AWS Advisor hướng đến giải quyết: giảm thời gian kiểm tra hạ tầng thủ công qua nhiều tab AWS Console.
* Nắm được các nhóm đối tượng sử dụng chính và nhu cầu tương ứng của từng nhóm.
* Hiểu tổng thể kiến trúc hệ thống: từ việc thu thập dữ liệu tự động, lưu trữ, phân tích bằng AI, đến hiển thị trên dashboard.
* Nắm được công nghệ dự kiến sử dụng ở cả backend, frontend và hạ tầng (Infrastructure as Code).
* Hiểu cấu trúc thư mục dự án và thiết kế Database Schema ban đầu.
* Nắm được API Contract dự kiến, làm cơ sở để triển khai ở các tuần tiếp theo.
