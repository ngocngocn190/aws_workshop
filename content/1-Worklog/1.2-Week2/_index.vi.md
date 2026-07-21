---
title: "Worklog Tuần 2"
date: 2025-05-25
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 2:

* Kết nối, làm quen với các thành viên trong First Cloud AI Journey.
* Hiểu dịch vụ AWS cơ bản, cách dùng console & CLI.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu tổng quan Amazon VPC <br>&emsp; + Subnets <br>&emsp; + Route Table <br>&emsp; + Internet Gateway <br>&emsp; + NAT Gateway                                                                                            | 25/05/2025   | 25/05/2025      | <https://000003.awsstudygroup.com/vi/3-prerequisite/>  |
| 3   | - Tìm hiểu tường lửa trong VPC <br>&emsp; + Security Group <br>&emsp; + Network ACLs <br>&emsp; + VPC Resource Map                                              | 26/05/2025   | 26/05/2025      | <https://000003.awsstudygroup.com/vi/3-prerequisite/>  |
| 4   | - **Thực hành:** Chuẩn bị môi trường VPC <br>&emsp; + Tạo VPC <br>&emsp; + Tạo Subnet <br>&emsp; + Tạo Internet Gateway <br>&emsp; + Tạo Route Table <br>&emsp; + Tạo Security Group <br>&emsp; + Kích hoạt VPC Flow Logs | 27/05/2025   | 27/05/2025      | <https://000003.awsstudygroup.com/vi/3-prerequisite/> |
| 5   | - **Thực hành:** Triển khai Amazon EC2 trong VPC <br>&emsp; + Tạo máy chủ EC2 <br>&emsp; + Kiểm tra kết nối <br>&emsp; + Tạo NAT Gateway <br>&emsp; + Sử dụng Reachability Analyzer <br>&emsp; + Session Manager & CloudWatch Monitoring               | 28/05/2025   | 28/05/2025      | <https://000003.awsstudygroup.com/vi/3-prerequisite/>  |
| 6   | - **Thực hành:** Cấu hình Site-to-Site VPN <br>&emsp; + Tạo môi trường VPN (VPC + EC2 riêng) <br>&emsp; + Tạo Virtual Private Gateway <br>&emsp; + Tạo Customer Gateway <br>&emsp; + Tạo kết nối VPN <br>&emsp; + Cấu hình Customer Gateway & tùy chỉnh VPN Tunnel                                                                                       | 29/05/2025   | 29/05/2025      | <https://000003.awsstudygroup.com/vi/3-prerequisite/>  |


### Kết quả đạt được tuần 2:

* Hiểu được kiến trúc và các thành phần cơ bản của Amazon VPC: Subnet, Route Table, Internet Gateway, NAT Gateway.
* Nắm được cách kiểm soát truy cập mạng bằng Security Group và Network ACL, phân biệt được sự khác nhau giữa hai loại này.
* Tự dựng được một môi trường VPC hoàn chỉnh và bật VPC Flow Logs để theo dõi lưu lượng.
* Triển khai thành công EC2 instance trong VPC, kiểm tra được kết nối và giám sát bằng CloudWatch.
* Thiết lập được kết nối AWS Site-to-Site VPN, hiểu luồng kết nối giữa Customer Gateway và Virtual Private Gateway.
* Biết cách dọn dẹp tài nguyên sau khi thực hành để tránh phát sinh chi phí ngoài ý muốn.
  
