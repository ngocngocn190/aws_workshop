---
title: "Blog 2"
date: 2026-06-06
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# AWS SHIELD ADVANCED ATTACK FLOW LOGS TRONG VIỆC GIÁM SÁT TẤN CÔNG DDOS

AWS Shield Advanced vừa bổ sung tính năng Attack Flow Logs, cho phép ghi lại thông tin chi tiết về lưu lượng trong quá trình xảy ra tấn công DDoS. Đây là bước cải tiến giúp đội vận hành phân tích và điều tra sự cố dựa trên dữ liệu cụ thể, thay vì chỉ nhìn vào các chỉ số tổng quan như trước.

Các điểm chính cần nắm:

* AWS Shield Advanced là dịch vụ bảo vệ DDoS nâng cao, hỗ trợ các tài nguyên như CloudFront, Elastic Load Balancing, Route 53, Global Accelerator và Elastic IP, có khả năng phát hiện và giảm thiểu tấn công ở tầng mạng và tầng vận chuyển.
* Attack Flow Logs ghi nhận metadata của lưu lượng trong thời gian diễn ra tấn công, và có thể xuất dữ liệu sang Amazon S3, CloudWatch Logs hoặc Amazon Data Firehose để tích hợp với hệ thống giám sát hiện có.
* Các trường dữ liệu được ghi nhận gồm: IP nguồn/đích, giao thức, số lượng packet/byte, quốc gia phát sinh lưu lượng, Edge Location tiếp nhận, và hành động mà Shield đã thực hiện với lưu lượng đó.
* Lợi ích chính: phân tích chi tiết quy mô và loại lưu lượng tấn công, xác định nguồn gốc tấn công qua IP/quốc gia, và kiểm tra hiệu quả của cơ chế giảm thiểu thông qua trường "action".
* Dữ liệu log có thể kết hợp với các công cụ phân tích như Amazon Athena, CloudWatch Logs Insights, hoặc các hệ thống SIEM như Splunk để phục vụ điều tra sâu hơn.

Tính năng này cho thấy việc chống DDoS hiệu quả không chỉ dừng ở phát hiện và ngăn chặn, mà khả năng quan sát, phân tích lưu lượng sau sự cố cũng quan trọng không kém để đánh giá mức độ ảnh hưởng và cải thiện hệ thống bảo mật về sau.

...Hình ảnh...

![AWS](images/i_blog2.png)

Link bài viết gốc: <https://aws.amazon.com/vi/blogs/security/gain-visibility-into-ddos-attacks-with-flow-logs-in-aws-shield-advanced/>

Link bài viết:<https://www.facebook.com/groups/660548818043427/user/100010448557887>