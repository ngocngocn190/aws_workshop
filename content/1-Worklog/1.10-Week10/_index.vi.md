---
title: "Worklog Tuần 10"
date: 2026-07-13
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Nội dung dưới đây là kế hoạch dự kiến, chỉ mang tính tham khảo, vui lòng **không sao chép nguyên văn** cho báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 10:

* Bắt đầu giai đoạn Core Build: triển khai Resource Collector và API backend cho dự án AI AWS Advisor.
* Hoàn thiện các tài liệu, cấu trúc dự án theo đúng yêu cầu chuẩn của Git repository.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------------------------- |
| 2   | - **Thực hành:** Setup cấu trúc SAM project (template.yaml, requirements.txt) <br> - Tạo 4 bảng DynamoDB (projects, resources, insights, alerts) | 13/07/2026   | 13/07/2026      |      |
| 3   | - **Thực hành:** Tạo IAM Role cho Collector Lambda (AssumeRole, least privilege permissions)                                            | 14/07/2026   | 14/07/2026      |      |
| 4   | - **Thực hành:** Xây dựng Resource Collector cho EC2 và S3 (thu thập instance, bucket, public access, ACL...)                          | 15/07/2026   | 15/07/2026      |      |
| 5   | - **Thực hành:** Xây dựng Resource Collector cho IAM, Lambda và CloudWatch                                                              | 16/07/2026   | 16/07/2026      |      |
| 6   | - **Thực hành:** Xây dựng API Lambda cho `/projects` (CRUD) và `/resources` (GET)                                                       | 17/07/2026   | 17/07/2026      |      |
| 7   | - Hoàn thiện tài liệu theo yêu cầu Git: README.md, .gitignore, docs/01-prerequisites.md <br> - Chuẩn hóa commit message & pull request theo branch strategy | 18/07/2026   | 18/07/2026      |      |

### Kết quả dự kiến đạt được tuần 10:

* Dựng được cấu trúc project chuẩn bằng AWS SAM và tạo xong 4 bảng DynamoDB theo schema đã chốt.
* Tạo được IAM Role riêng cho Collector Lambda, tuân thủ nguyên tắc least privilege.
* Resource Collector cho EC2 và S3 hoạt động, dữ liệu được ghi vào DynamoDB.
* Resource Collector cho IAM, Lambda và CloudWatch hoạt động, hoàn thiện việc thu thập dữ liệu hạ tầng.
* API `/projects` và `/resources` hoạt động, trả về dữ liệu đúng như API Contract đã chốt.
* Repository trên GitHub có đầy đủ README, .gitignore, tài liệu chuẩn bị (prerequisites), và tuân thủ quy tắc nhánh (branch) đã thống nhất trong nhóm.
* ...