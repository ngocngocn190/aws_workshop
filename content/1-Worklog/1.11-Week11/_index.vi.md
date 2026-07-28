---
title: "Worklog Tuần 11"
date: 2026-07-20
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---



### Mục tiêu tuần 11:

* Hoàn thiện tích hợp AI (Amazon Bedrock) và xây dựng Frontend cho dự án AI AWS Advisor.
* Kết nối toàn bộ luồng end-to-end và tiếp tục hoàn thiện tài liệu dự án theo chuẩn Git.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------------------------- |
| 2   | - **Thực hành:** Xây dựng AI Analyzer gọi Amazon Bedrock, viết prompt templates cho Security/Cost/Performance/Chat                     | 20/07/2026   | 20/07/2026      |      |
| 3   | - **Thực hành:** Setup Frontend (React + Vite + Tailwind + shadcn/ui), dựng layout Sidebar & Header                                    | 21/07/2026   | 21/07/2026      |      |
| 4   | - **Thực hành:** Xây dựng các trang Dashboard, Security, Cost, Performance                                                              | 22/07/2026   | 22/07/2026      |      |
| 5   | - **Thực hành:** Kết nối Frontend với API backend, test luồng end-to-end (tạo project → sync → xem resources/insights)                 | 23/07/2026   | 23/07/2026      |      |
| 6   | - **Thực hành:** Thiết lập EventBridge Scheduler (trigger Collector mỗi giờ) và SNS Alert khi có Critical risk                          | 24/07/2026   | 24/07/2026      |      |
| 7   | - Hoàn thiện tài liệu theo yêu cầu Git: docs/02-architecture.md, docs/03-deployment.md, docs/04-testing.md                              | 25/07/2026   | 25/07/2026      |      |

### Kết quả dự kiến đạt được tuần 11:

* AI Analyzer gọi thành công Amazon Bedrock, trả về phân tích bảo mật/chi phí/hiệu năng và trả lời chat dựa trên dữ liệu thật.
* Frontend hiển thị được Dashboard, danh sách rủi ro bảo mật, biểu đồ chi phí và hiệu năng.
* Luồng end-to-end hoạt động: từ tạo project, đồng bộ dữ liệu, đến hiển thị insight trên giao diện.
* EventBridge tự động trigger Collector mỗi giờ; SNS gửi email cảnh báo khi phát hiện rủi ro Critical.
* Tài liệu kiến trúc, hướng dẫn triển khai và kiểm thử được viết đầy đủ, tuân thủ chuẩn cấu trúc docs của repository.
* ...