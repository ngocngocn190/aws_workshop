---
title: "Bản đề xuất"
date: 2026-06-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Tại phần này, bạn cần tóm tắt các nội dung trong workshop mà bạn **dự tính** sẽ làm.

# AI AWS Advisor
## Cloud Operations Copilot - Trợ lý AI giúp Cloud Engineer & DevOps quản trị, phân tích và tối ưu hạ tầng AWS tự động
 

### 1. Tóm tắt điều hành  
AI AWS Advisor là nền tảng quản trị hạ tầng AWS thông minh, hoạt động như một Cloud Operations Copilot dành cho Cloud Engineer, DevOps Engineer, Solution Architect, System Administrator và Technical Manager. Thay vì phải mở nhiều tab AWS Console để kiểm tra từng dịch vụ, người dùng chỉ cần kết nối tài khoản AWS một lần thông qua IAM Role ARN (không lưu Access Key). Hệ thống sẽ tự động quét toàn bộ hạ tầng mỗi giờ, AI phân tích và đưa ra cảnh báo cùng khuyến nghị, hiển thị trên một dashboard duy nhất, đồng thời cho phép hỏi đáp bằng ngôn ngữ tự nhiên (tiếng Việt hoặc tiếng Anh) về bất kỳ vấn đề nào của hệ thống.
### 2. Tuyên bố vấn đề  
*Vấn đề hiện tại*  
Doanh nghiệp dùng AWS thường gặp các vấn đề như: không biết có bao nhiêu EC2 đang chạy mà không ai dùng, S3 bucket nào đang bị public ra internet, IAM Role nào có quyền quá rộng (AdministratorAccess), Lambda nào cấu hình dư thừa so với nhu cầu thực tế, dịch vụ nào đang tốn chi phí nhiều nhất, và hệ thống đang có những rủi ro bảo mật nào. Để trả lời những câu hỏi này theo cách truyền thống, người dùng phải mở lần lượt EC2, S3, IAM, CloudWatch trên AWS Console rồi tổng hợp thủ công, mất khoảng 1-2 giờ.

*Giải pháp*  
AI AWS Advisor tự động thu thập dữ liệu qua các Resource Collector Lambda (EC2, S3, IAM, Lambda, CloudWatch) mỗi giờ thông qua EventBridge Scheduler, sử dụng AssumeRole để truy cập tài khoản AWS mục tiêu một cách an toàn, lưu dữ liệu vào DynamoDB. Amazon Bedrock (Claude AI) sau đó phân tích dữ liệu và sinh ra insight về bảo mật, chi phí và hiệu năng; hệ thống tự động phân loại rủi ro theo mức độ (Critical/High/Medium/Low) và gửi cảnh báo qua Amazon SNS khi phát hiện rủi ro Critical. Người dùng cũng có thể trò chuyện trực tiếp với AI Copilot để hỏi đáp về hạ tầng. Toàn bộ quy trình được giải quyết trong dưới 30 giây, thay vì 1-2 giờ theo cách thủ công. 



#### Hiệu quả Kinh tế & Tối ưu (ROI)
- **Tiết kiệm Thời gian:** Giảm hơn 90% thời gian kiểm toán thủ công (từ nhiều ngày xuống còn vài phút).
- **Tối ưu Chi phí:** Phát hiện từ 15% đến 35% chi phí lãng phí hàng tháng cho khách hàng.
- **Chi phí duy trì nhàn rỗi (Idle Cost):** Hệ thống sử dụng kiến trúc Serverless theo mô hình pay-per-use, vì vậy khi không có yêu cầu xử lý, chi phí vận hành gần như bằng **0 USD/tháng**.


### 3. Kiến trúc giải pháp  
Nền tảng áp dụng kiến trúc AWS Serverless. React Dashboard (frontend) giao tiếp qua HTTPS với Amazon API Gateway, API Gateway gọi các Lambda xử lý nghiệp vụ (Projects API, Resources API, AI Analyze API), dữ liệu được lưu trong DynamoDB (4 bảng: projects, resources, insights, alerts). Amazon EventBridge Scheduler kích hoạt các Resource Collector Lambda (ec2_collector, s3_collector, iam_collector, lambda_collector, cloudwatch_collector) mỗi giờ; các Lambda này dùng AssumeRole để truy cập tài khoản AWS mục tiêu và thu thập dữ liệu từ EC2, S3, IAM, Lambda, CloudWatch, RDS. Amazon Bedrock (Claude) nhận dữ liệu, phân tích và trả về insight; Amazon SNS gửi email khi phát hiện cảnh báo Critical.

![IoT Weather Station Architecture](/images/2-Proposal/edge_architecture.jpeg)

![IoT Weather Platform Architecture](/images/2-Proposal/platform_architecture.jpeg)

*Dịch vụ AWS sử dụng*  
- *AWS Lambda*: Serverless, không cần quản lý server, tự scale, pay-per-use.
- *Amazon API Gateway*: Managed, tích hợp native với Lambda, có auth built-in.
- *Amazon DynamoDB*: Serverless, low latency, schema linh hoạt phù hợp dữ liệu đa dạng từ nhiều AWS service.
- *Amazon EventBridge*: Scheduler gốc của AWS, cron expression đơn giản, đáng tin cậy.
- *Amazon Bedrock*: Dịch vụ AI được quản lý bởi AWS, không cần tự host model, có Claude.
- *Amazon SNS*: Đơn giản, managed, dễ tích hợp với Lambda.
- *Amazon CloudWatch*: Giám sát gốc của AWS, không cần setup thêm hạ tầng, lưu log tự động. 

 

### 4. Triển khai kỹ thuật  CHƯA LÀM LẠI
*Các giai đoạn triển khai*  
#### Các Giai đoạn Thực hiện
1. **Giai đoạn 1: Bảo mật & Thiết kế Kiến trúc:** Thiết lập Trust Policy IAM Cross-Account, cấu hình template IaC với AWS SAM CLI và thiết kế Single-Table schema DynamoDB (`PROJECTS`, `RESOURCES`, `INSIGHTS`, `ALERTS`).
2. **Giai đoạn 2: Phát triển Scanner & Tích hợp Bedrock:** Lập trình bộ thu thập cấu hình bằng `boto3`, viết Prompt Engineering cho Claude 3 trên Bedrock và xây dựng bộ kiểm thử Pytest/Moto.
3. **Giai đoạn 3: Phát triển Dashboard & AI Chatbot:** Xây dựng giao diện React 18 với Vite, Tailwind CSS và Recharts; tích hợp AI Chatbot Copilot; kiểm thử toàn diện và đóng gói CloudFormation deployment.


### 5. Lộ trình & Mốc triển khai  
- *Phase 0 – Foundation (Tuần 1)*: Tạo AWS Account sandbox, setup IAM User cho team, tạo GitHub repo, chốt DynamoDB schema và API contract, chuẩn bị môi trường local, enable Amazon Bedrock trên AWS Console.
- *Phase 1 – Core Build (Tuần 2–3)*: Tạo DynamoDB tables và IAM Role cho Collector; EC2/S3/IAM/Lambda Collector hoạt động và ghi data vào DynamoDB; API /projects và /resources hoạt động; AI analyzer gọi được Bedrock; Frontend kết nối API và hiển thị dữ liệu thật.
- *Phase 2 – Integration (Tuần 3–4)*: EventBridge trigger Collector mỗi giờ; AI tự động phân tích sau mỗi lần collect; SNS gửi email khi có rủi ro Critical; Chat endpoint hoạt động; Frontend hiển thị AI insights; demo end-to-end hoàn chỉnh.
- *Phase 3 – Docs & Polish (Tuần 4–5)*: Hoàn thiện workshop guide song ngữ Anh/Việt, chụp đầy đủ screenshot, viết clean-up guide, viết reflection từng thành viên, final review theo rubric.

### 6. Ước tính ngân sách  CHƯA LÀM LẠI
Có thể xem chi phí trên [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=621f38b12a1ef026842ba2ddfe46ff936ed4ab01)  
Hoặc tải [tệp ước tính ngân sách](../attachments/budget_estimation.pdf).  

*Chi phí hạ tầng*  
Chi phí ước tính hàng tháng trên 10 dự án khách hàng quét 1,000 tài nguyên AWS mỗi ngày:

| Dịch vụ AWS | Mức độ Sử dụng | Chi phí Ước tính / Tháng |
| :--- | :--- | :--- |
| **AWS Lambda** | 100,000 requests, 512 MB memory | $0.00 (Free Tier) |
| **Amazon API Gateway** | 50,000 REST requests | $0.05 |
| **Amazon DynamoDB** | On-Demand (2 GB storage, 500k reads/writes) | $0.25 |
| **Amazon Bedrock** | Claude 3 Haiku (1M Input tokens, 200k Output tokens) | $1.20 |
| **Amazon EventBridge & SNS** | 720 triggers/tháng, 100 emails | $0.01 |
| **Tổng Chi phí Ước tính Tháng** | **Serverless Pay-Per-Use** | **~$1.51 / tháng** |

*Tổng Chi phí Hạ tầng Hàng năm:* **~$18.12 USD / năm**.

---



### 7. Đánh giá Rủi ro & Giải pháp Giảm thiểu

| Rủi ro phát hiện | Mức độ | Khả năng xảy ra | Giải pháp giảm thiểu |
| :--- | :--- | :--- | :--- |
| **Giới hạn Rate Limit của Amazon Bedrock API** | Trung bình | Thấp | Cấu hình cơ chế **retry theo exponential backoff** và lưu cache kết quả trên DynamoDB để giảm số lần gọi API. |
| **Khách hàng thu hồi quyền IAM Role** | Cao | Trung bình | Bắt ngoại lệ `ClientError` khi thực hiện `sts:AssumeRole` và tự động cập nhật trạng thái của project thành **Disconnected**. |
| **LLM tạo ra kết quả không chính xác (Hallucination)** | Cao | Thấp | Yêu cầu mô hình trả về dữ liệu theo **JSON schema** cố định và sử dụng **regex fallback parser** trong Python để kiểm tra, xử lý khi kết quả không đúng định dạng. |
| **Vượt ngân sách sử dụng AWS** | Trung bình | Thấp | Thiết lập **AWS Budgets** để gửi cảnh báo khi chi phí đạt **5 USD/tháng** và giới hạn tần suất chạy của các tác vụ theo lịch (cron jobs). |

---

### 8. Kết quả Kỳ vọng

1. **Tự động hóa quy trình kiểm toán:** Xây dựng hệ thống AI có khả năng tự động kiểm tra và đánh giá tài nguyên AWS theo chu kỳ mỗi giờ, giảm sự phụ thuộc vào việc rà soát thủ công.

2. **Đảm bảo an toàn thông tin:** Hạn chế rủi ro lộ thông tin xác thực (credentials) bằng cách sử dụng **session token ngắn hạn** thông qua cơ chế `sts:AssumeRole`.

3. **Mô hình tham khảo cho doanh nghiệp:** Xây dựng một kiến trúc mẫu (blueprint) có thể tái sử dụng để phát triển các ứng dụng **B2B SaaS** dựa trên kiến trúc **Serverless** của AWS.