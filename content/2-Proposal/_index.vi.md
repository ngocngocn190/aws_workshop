---
title: "Bản đề xuất"
date: 2024-01-01
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



*Lợi ích và hoàn vốn đầu tư (ROI)*  CHƯA LÀM LẠI
Giải pháp tạo nền tảng cơ bản để các thành viên phòng lab phát triển một nền tảng IoT lớn hơn, đồng thời cung cấp nguồn dữ liệu cho những người nghiên cứu AI phục vụ huấn luyện mô hình hoặc phân tích. Nền tảng giảm bớt báo cáo thủ công cho từng trạm thông qua hệ thống tập trung, đơn giản hóa quản lý và bảo trì, đồng thời cải thiện độ tin cậy dữ liệu. Chi phí hàng tháng ước tính 0,66 USD (theo AWS Pricing Calculator), tổng cộng 7,92 USD cho 12 tháng. Tất cả thiết bị IoT đã được trang bị từ hệ thống trạm thời tiết hiện tại, không phát sinh chi phí phát triển thêm. Thời gian hoàn vốn 6–12 tháng nhờ tiết kiệm đáng kể thời gian thao tác thủ công.  



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

*Thiết kế thành phần*  CHƯA LÀM LẠI
- *Thiết bị biên*: Raspberry Pi thu thập và lọc dữ liệu cảm biến, gửi tới IoT Core.  
- *Tiếp nhận dữ liệu*: AWS IoT Core nhận tin nhắn MQTT từ thiết bị biên.  
- *Lưu trữ dữ liệu*: Dữ liệu thô lưu trong S3 data lake; dữ liệu đã xử lý lưu ở một S3 bucket khác.  
- *Xử lý dữ liệu*: AWS Glue Crawlers lập chỉ mục dữ liệu; ETL jobs chuyển đổi để phân tích.  
- *Giao diện web*: AWS Amplify lưu trữ ứng dụng Next.js cho bảng điều khiển và phân tích thời gian thực.  
- *Quản lý người dùng*: Amazon Cognito giới hạn 5 tài khoản hoạt động.  

### 4. Triển khai kỹ thuật  CHƯA LÀM LẠI
*Các giai đoạn triển khai*  
Dự án gồm 2 phần — thiết lập trạm thời tiết biên và xây dựng nền tảng thời tiết — mỗi phần trải qua 4 giai đoạn:  
1. *Nghiên cứu và vẽ kiến trúc*: Nghiên cứu Raspberry Pi với cảm biến ESP32 và thiết kế kiến trúc AWS Serverless (1 tháng trước kỳ thực tập).  
2. *Tính toán chi phí và kiểm tra tính khả thi*: Sử dụng AWS Pricing Calculator để ước tính và điều chỉnh (Tháng 1).  
3. *Điều chỉnh kiến trúc để tối ưu chi phí/giải pháp*: Tinh chỉnh (ví dụ tối ưu Lambda với Next.js) để đảm bảo hiệu quả (Tháng 2).  
4. *Phát triển, kiểm thử, triển khai*: Lập trình Raspberry Pi, AWS services với CDK/SDK và ứng dụng Next.js, sau đó kiểm thử và đưa vào vận hành (Tháng 2–3).  

*Yêu cầu kỹ thuật*  
- *Trạm thời tiết biên*: Cảm biến (nhiệt độ, độ ẩm, lượng mưa, tốc độ gió), vi điều khiển ESP32, Raspberry Pi làm thiết bị biên. Raspberry Pi chạy Raspbian, sử dụng Docker để lọc dữ liệu và gửi 1 MB/ngày/trạm qua MQTT qua Wi-Fi.  
- *Nền tảng thời tiết*: Kiến thức thực tế về AWS Amplify (lưu trữ Next.js), Lambda (giảm thiểu do Next.js xử lý), AWS Glue (ETL), S3 (2 bucket), IoT Core (gateway và rules), và Cognito (5 người dùng). Sử dụng AWS CDK/SDK để lập trình (ví dụ IoT Core rules tới S3). Next.js giúp giảm tải Lambda cho ứng dụng web fullstack.  

### 5. Lộ trình & Mốc triển khai  
- *Phase 0 – Foundation (Tuần 1)*: Tạo AWS Account sandbox, setup IAM User cho team, tạo GitHub repo, chốt DynamoDB schema và API contract, chuẩn bị môi trường local, enable Amazon Bedrock trên AWS Console.
- *Phase 1 – Core Build (Tuần 2–3)*: Tạo DynamoDB tables và IAM Role cho Collector; EC2/S3/IAM/Lambda Collector hoạt động và ghi data vào DynamoDB; API /projects và /resources hoạt động; AI analyzer gọi được Bedrock; Frontend kết nối API và hiển thị dữ liệu thật.
- *Phase 2 – Integration (Tuần 3–4)*: EventBridge trigger Collector mỗi giờ; AI tự động phân tích sau mỗi lần collect; SNS gửi email khi có rủi ro Critical; Chat endpoint hoạt động; Frontend hiển thị AI insights; demo end-to-end hoàn chỉnh.
- *Phase 3 – Docs & Polish (Tuần 4–5)*: Hoàn thiện workshop guide song ngữ Anh/Việt, chụp đầy đủ screenshot, viết clean-up guide, viết reflection từng thành viên, final review theo rubric.

### 6. Ước tính ngân sách  CHƯA LÀM LẠI
Có thể xem chi phí trên [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=621f38b12a1ef026842ba2ddfe46ff936ed4ab01)  
Hoặc tải [tệp ước tính ngân sách](../attachments/budget_estimation.pdf).  

*Chi phí hạ tầng*  
- AWS Lambda: 0,00 USD/tháng (1.000 request, 512 MB lưu trữ).  
- S3 Standard: 0,15 USD/tháng (6 GB, 2.100 request, 1 GB quét).  
- Truyền dữ liệu: 0,02 USD/tháng (1 GB vào, 1 GB ra).  
- AWS Amplify: 0,35 USD/tháng (256 MB, request 500 ms).  
- Amazon API Gateway: 0,01 USD/tháng (2.000 request).  
- AWS Glue ETL Jobs: 0,02 USD/tháng (2 DPU).  
- AWS Glue Crawlers: 0,07 USD/tháng (1 crawler).  
- MQTT (IoT Core): 0,08 USD/tháng (5 thiết bị, 45.000 tin nhắn).  

*Tổng*: 0,7 USD/tháng, 8,40 USD/12 tháng  
- *Phần cứng*: 265 USD một lần (Raspberry Pi 5 và cảm biến).  

### 7. Đánh giá rủi ro  CHƯA LÀM LẠI
*Ma trận rủi ro*  
- Mất mạng: Ảnh hưởng trung bình, xác suất trung bình.  
- Hỏng cảm biến: Ảnh hưởng cao, xác suất thấp.  
- Vượt ngân sách: Ảnh hưởng trung bình, xác suất thấp.  

*Chiến lược giảm thiểu*  
- Mạng: Lưu trữ cục bộ trên Raspberry Pi với Docker.  
- Cảm biến: Kiểm tra định kỳ, dự phòng linh kiện.  
- Chi phí: Cảnh báo ngân sách AWS, tối ưu dịch vụ.  

*Kế hoạch dự phòng*  
- Quay lại thu thập thủ công nếu AWS gặp sự cố.  
- Sử dụng CloudFormation để khôi phục cấu hình liên quan đến chi phí.  

### 8. Kết quả kỳ vọng  CHƯA LÀM LẠI
*Cải tiến kỹ thuật*: Dữ liệu và phân tích thời gian thực thay thế quy trình thủ công. Có thể mở rộng tới 10–15 trạm.  
*Giá trị dài hạn*: Nền tảng dữ liệu 1 năm cho nghiên cứu AI, có thể tái sử dụng cho các dự án tương lai.