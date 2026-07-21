---
title: "Event 3"
date: 2026-07-18
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Bài thu hoạch Seminar "AI From Scratch"

### Mục Đích Của Sự Kiện

- Giới thiệu quy trình xây dựng một hệ thống AI hoàn chỉnh từ đầu bằng các dịch vụ trên AWS
- Giới thiệu Amazon SageMaker AI để huấn luyện và triển khai mô hình machine learning
- Giới thiệu Amazon Bedrock và cách tiếp cận các mô hình nền tảng (foundation models) có sẵn
- Giới thiệu khái niệm Embedding và kỹ thuật RAG (Retrieval-Augmented Generation) để kiểm soát nội dung đầu ra của AI

### Danh Sách Diễn Giả

- **Nguyễn Tuấn Thịnh** - DevOps/Cloud Engineer - AWS
- **Nguyễn Công Minh** - DevOps Engineer - AWS
- Các chuyên viên từ **AWS Vietnam**
- Giảng viên phụ trách chuyên môn: **Thầy Mai Hoàng Đỉnh** – Giảng viên IA – FPTU HCMC

### Nội Dung Nổi Bật

#### Quy trình xây dựng một hệ thống AI hoàn chỉnh trên AWS

- Đi từ bước thu thập, xử lý dữ liệu đầu vào đến huấn luyện, triển khai và giám sát mô hình.
- Vai trò của từng dịch vụ AWS trong một pipeline AI end-to-end, từ dữ liệu thô đến ứng dụng thực tế.

#### Nhận diện giọng nói (Speech Recognition) trên AWS

- Chuyển đổi giọng nói thành văn bản (speech-to-text) để làm đầu vào cho các mô hình xử lý ngôn ngữ.
- Ứng dụng thực tế trong chatbot thoại, trợ lý ảo, xử lý dữ liệu âm thanh quy mô lớn.

#### Amazon SageMaker AI

- Nền tảng để chuẩn bị dữ liệu, huấn luyện, tinh chỉnh (fine-tune), đánh giá và triển khai mô hình machine learning.
- Quản lý toàn bộ vòng đời (lifecycle) của một mô hình AI tự huấn luyện.

#### Amazon Bedrock

- Nền tảng cho phép truy cập nhiều mô hình nền tảng (foundation models) từ các nhà cung cấp khác nhau (Anthropic, Meta, Amazon...) thông qua một API thống nhất.
- Giúp xây dựng ứng dụng generative AI nhanh chóng mà không cần tự huấn luyện mô hình từ đầu.

#### Embedding

- Khái niệm biểu diễn văn bản, hình ảnh hoặc dữ liệu dưới dạng vector số học, giúp máy tính "hiểu" và so sánh được mức độ tương đồng về ngữ nghĩa.
- Là nền tảng cho các tác vụ tìm kiếm ngữ nghĩa (semantic search), phân cụm dữ liệu, và đặc biệt là bước truy xuất trong kiến trúc RAG.
- AWS cung cấp các mô hình embedding thông qua Amazon Bedrock để chuyển đổi dữ liệu văn bản thành vector, lưu trữ trong vector database phục vụ truy vấn.

#### RAG (Retrieval-Augmented Generation)

- Kỹ thuật kết hợp bước truy xuất dữ liệu (retrieval) từ nguồn dữ liệu riêng với khả năng sinh văn bản (generation) của mô hình ngôn ngữ lớn (LLM).
- Giúp mô hình trả lời chính xác và bám sát nguồn dữ liệu được kiểm soát, thay vì chỉ dựa vào kiến thức đã huấn luyện sẵn.
- Được ứng dụng để kiểm soát nội dung đầu ra của AI: giới hạn phạm vi trả lời trong nguồn dữ liệu đáng tin cậy, kết hợp guardrails để hạn chế ngôn từ bạo lực hoặc nội dung không phù hợp.

### Những Gì Học Được

#### Tư duy xây dựng hệ thống AI toàn diện

- Hiểu vai trò của từng lớp trong kiến trúc AI: lớp dữ liệu đầu vào (giọng nói, văn bản), lớp mô hình nền tảng, và lớp kiểm soát đầu ra.
- Hiểu khái niệm Embedding và vai trò của nó trong việc biểu diễn ngữ nghĩa cho dữ liệu.
- Hiểu kiến trúc RAG và lý do kỹ thuật này giúp kiểm soát output của LLM tốt hơn so với chỉ fine-tune mô hình trong nhiều trường hợp.
- Hiểu cách RAG kết hợp với các cơ chế lọc, giới hạn nguồn dữ liệu để hạn chế AI sinh ra ngôn từ bạo lực hoặc nội dung không phù hợp.
- Nhận thấy vai trò quan trọng của guardrails trong việc đảm bảo hệ thống AI hoạt động an toàn, đúng phạm vi cho phép.
- Các diễn giả đến từ AWS Vietnam đã chia sẻ trực tiếp kinh nghiệm triển khai các dịch vụ AI trên AWS trong dự án thực tế.
- Nhận ra tầm quan trọng của việc thiết kế hệ thống AI có kiểm soát ngay từ đầu, thay vì chỉ tập trung vào độ chính xác của mô hình.
#### Kết nối và trao đổi
- Buổi Q&A tạo cơ hội trao đổi trực tiếp với các kỹ sư AWS về những vấn đề thực tế khi triển khai AI 
- Qua các câu hỏi và chia sẻ, có thêm góc nhìn thực tế về những thách thức khi đưa một hệ thống AI từ demo lên production.

#### Bài học rút ra
- Một hệ thống AI hoàn chỉnh không chỉ gồm mô hình, mà còn cần các lớp xử lý dữ liệu đầu vào, lớp truy xuất thông tin (retrieval), và lớp kiểm soát đầu ra.
- Embedding và RAG là hai kỹ thuật nền tảng giúp AI trả lời chính xác hơn và an toàn hơn khi làm việc với dữ liệu riêng của tổ chức.
- Việc lựa chọn giữa tự huấn luyện mô hình (SageMaker) và sử dụng mô hình nền tảng có sẵn (Bedrock) cần dựa trên use-case cụ thể, không nên áp dụng một cách máy móc.

#### Một số hình ảnh khi tham gia sự kiện
* Thêm các hình ảnh của các bạn tại đây

