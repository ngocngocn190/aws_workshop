---
title: "Các bài blogs đã đăng"
date: 2026-07-20
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

{{% notice warning %}}  
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Tại đây sẽ là phần liệt kê, giới thiệu các blogs mà các bạn đã đăng trên [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj). Ví dụ:

###  [Blog 1 - TÌM HIỂU AI TRAFFIC ANALYSIS DASHBOARDS TRONG AWS WAF](3.1-Blog1/)
Blog này tóm tắt tính năng mới của AWS WAF là AI Traffic Analysis Dashboards, giúp đội vận hành quan sát và phân tích riêng biệt lượng truy cập đến từ các hệ thống AI (AI crawler/agent) thay vì gộp chung với bot truyền thống. Dashboard cho biết những crawler nào đang hoạt động, mức độ truy cập, và những URL/endpoint đang chịu tải AI traffic lớn nhất, giúp doanh nghiệp có cái nhìn rõ ràng hơn về loại lưu lượng này trên hệ thống của mình.

###  [Blog 2 - AWS SHIELD ADVANCED ATTACK FLOW LOGS TRONG VIỆC GIÁM SÁT TẤN CÔNG DDOS](3.2-Blog2/)
Blog này giới thiệu tính năng Attack Flow Logs của AWS Shield Advanced, cho phép ghi lại chi tiết thông tin lưu lượng trong quá trình xảy ra tấn công DDoS (IP nguồn/đích, giao thức, quốc gia phát sinh, hành động xử lý...) và xuất dữ liệu sang S3, CloudWatch Logs hoặc Data Firehose để phục vụ phân tích, điều tra sự cố sâu hơn.

###  [Blog 3 - NHÌN LẠI KIẾN TRÚC HIỆN ĐẠI HÓA QUY TRÌNH KYC BẰNG SERVERLESS & AGENTIC AI TRÊN AWS](3.3-Blog3/)
Blog này phân tích một whitepaper của AWS và IBM về kiến trúc hiện đại hóa quy trình KYC cho ngân hàng bằng agentic AI, event-driven architecture (Amazon MSK) và RAG với knowledge base. Bên cạnh việc ghi nhận những quyết định kiến trúc hợp lý, bài viết cũng chỉ ra các khoảng trống cần làm rõ như số liệu chưa có minh chứng thực nghiệm, trách nhiệm pháp lý khi AI quyết định sai, và các nguy cơ bảo mật như deepfake hay tấn công danh tính tổng hợp.