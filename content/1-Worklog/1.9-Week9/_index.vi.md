---
title: "Worklog Tuần 9"
date: 2026-07-06
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Nội dung dưới đây là kế hoạch dự kiến, chỉ mang tính tham khảo, vui lòng **không sao chép nguyên văn** cho báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 9:

* Hoàn thiện việc phân chia công việc và chuẩn bị nền tảng (Foundation) cho dự án AI AWS Advisor.
* Tìm hiểu Amazon Bedrock cơ bản: khái niệm, cách hoạt động và cách gọi model để phục vụ tính năng AI Copilot của dự án.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                  | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | -------------------------------- |
| 2   | - Phân chia công việc trong nhóm theo từng vai trò (Backend API, Resource Collector, AI Integration, Frontend, DevOps & Docs)              | 06/07/2026   | 06/07/2026      |      |
| 3   | - **Thực hành:** Tạo AWS Account sandbox, setup IAM User cho nhóm <br> - Tạo GitHub repo, thiết lập branch strategy (main, dev, feature/*) | 07/07/2026   | 07/07/2026      |      |
| 4   | - Tìm hiểu tổng quan Amazon Bedrock: foundation model là gì, các nhà cung cấp model (Anthropic, Meta, Amazon...)                          | 08/07/2026   | 08/07/2026      |      |
| 5   | - **Thực hành:** Enable Amazon Bedrock trong AWS Console (request access model) <br> - Gọi thử model Claude 3 Haiku/Sonnet qua Bedrock    | 09/07/2026   | 09/07/2026      |      |
| 6   | - Tìm hiểu cách viết prompt cơ bản cho Bedrock: prompt cho Security Analysis, Cost Recommendation, Performance Insight                     | 10/07/2026   | 10/07/2026      |      |
| 7   | - Chốt DynamoDB Schema và API Contract cho dự án (không thay đổi sau mốc này để tránh ảnh hưởng tiến độ nhóm)                              | 11/07/2026   | 11/07/2026      |      |

### Kết quả dự kiến đạt được tuần 9:

* Có bảng phân chia công việc rõ ràng cho từng thành viên trong nhóm.
* Chuẩn bị xong nền tảng ban đầu: AWS sandbox account, IAM User, GitHub repo với chiến lược branch rõ ràng.
* Hiểu Amazon Bedrock là gì, vai trò của nó trong việc cung cấp mô hình AI được quản lý (managed AI service) mà không cần tự host model.
* Tự enable được Amazon Bedrock và gọi thử thành công model Claude qua Bedrock.
* Biết cách viết prompt cơ bản để yêu cầu AI phân tích bảo mật, chi phí hoặc hiệu năng.
* Chốt được DynamoDB Schema và API Contract, làm nền tảng ổn định để cả nhóm cùng triển khai song song ở các tuần sau.
