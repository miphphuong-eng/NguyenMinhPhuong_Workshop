---
title: "Nhật ký thực tập Tuần 1"
weight: 1
draft: false
---

# NHẬT KÝ THỰC TẬP TUẦN 1

## Mục tiêu Tuần 1:

* Giao lưu và làm quen với các thành viên trong chương trình First Cloud AI Journey (FCAJ).
* Hiểu rõ các quy định, yêu cầu và lộ trình học tập của FCAJ.
* Nắm vững các khái niệm cơ bản về Điện toán đám mây (Cloud Computing) và Amazon Web Services (AWS).
* Tìm hiểu các nhóm dịch vụ cốt lõi của AWS:
  * Compute (Điện toán)
  * Storage (Lưu trữ)
  * Networking (Mạng)
  * Database (Cơ sở dữ liệu)
* Tạo và bảo mật tài khoản AWS, tìm hiểu các chính sách của gói AWS Free Tier.
* Học cách sử dụng giao diện quản trị AWS Management Console và giao diện dòng lệnh AWS CLI.
* Hiểu các khái niệm về Amazon EC2 và thực hành các bài lab EC2 cơ bản.
* Tìm hiểu về chương trình AWS Free Tier 2025 và khoản tín dụng **$200 AWS Credit**.
* Thực hành các bài tập thực tế với các dịch vụ AWS quan trọng, bao gồm:
  * Amazon EC2
  * Amazon Bedrock
  * AWS Budgets
  * AWS Lambda
  * Amazon RDS
* Học cách giám sát tài nguyên AWS, kiểm soát chi phí và dọn dẹp các tài nguyên không sử dụng.
* Thành lập nhóm học tập và chuẩn bị cho các dự án AWS tiếp theo.

---

## Các công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|:---:|------|:----------:|:---------------:|--------------------|
| **2** | - Giao lưu và làm quen với các thành viên FCAJ.<br>- Đọc và ghi chú quy định của đơn vị thực tập. | **21/09/2026** | **21/09/2026** | **FCAJ Regulations** |
| **3** | - Tìm hiểu nền tảng Điện toán đám mây và tổng quan AWS.<br>- Tìm hiểu các nhóm dịch vụ AWS cốt lõi.<br>- Thực hiện các bài lab nhập môn về Compute (EC2), Storage (S3), Networking (VPC) và Database (RDS). | **21/09/2026** | **21/09/2026** | **AWS Cloud Journey**<br>**AWS Overview** |
| **4** | - Tạo và bảo mật tài khoản AWS Free Tier.<br>- Thiết lập xác thực hai yếu tố Multi-Factor Authentication (MFA).<br>- Kiểm tra các cài đặt liên quan đến thanh toán.<br>- Làm quen với giao diện AWS Management Console.<br>- Cài đặt và cấu hình AWS CLI với profile mặc định. | **22/09/2026** | **22/09/2026** | **AWS Cloud Journey**<br>**AWS Free Tier**<br>**AWS CLI User Guide** |
| **5** | - Tìm hiểu các khái niệm cơ bản về Amazon EC2.<br>- Học về AMI, Instance Types, EBS, Security Groups, Key Pairs và Elastic IP.<br>- Hiểu vai trò của từng thành phần trong việc quản lý một EC2 instance. | **22/09/2026** | **22/09/2026** | **AWS Cloud Journey**<br>**Amazon EC2 Guide** |
| **6** | - Khởi tạo một Amazon EC2 instance.<br>- Tạo và cấu hình Key Pair cùng Security Group.<br>- Kết nối với EC2 instance thông qua SSH.<br>- Tạo, gắn (attach) và kiểm tra ổ đĩa EBS volume.<br>- Thực hành xóa (terminate) tài nguyên sau khi hoàn thành bài lab. | **23/09/2026** | **23/09/2026** | **AWS Cloud Journey**<br>**Amazon EBS User Guide** |
| **7** | - Tìm hiểu chương trình AWS Free Tier 2025 dành cho tài khoản đủ điều kiện tạo sau ngày 15/07/2025.<br>- Hiểu cấu trúc Free Tier mới và chương trình tín dụng **$200 AWS Credit**.<br>- Phân biệt gói Free Account Plan và Paid Account Plan.<br>- Học cách nhận và sử dụng AWS Credits qua bài thực hành.<br>- Học cách quản lý chi phí, giám sát và dọn dẹp tài nguyên. | **23/09/2026** | **23/09/2026** | **AWS Free Tier**<br>**AWS Free Tier 2025 Guide** |
| **8** | - Thực hành **AWS Free Tier Task 1: Launch an EC2 Instance**.<br>- Khởi chạy EC2 instance sử dụng AMI.<br>- Cấu hình thông số phần cứng và Key Pair.<br>- Tạo Security Group.<br>- Khởi chạy và kiểm tra instance.<br>- Terminate instance sau khi hoàn thành bài lab. | **24/09/2026** | **24/09/2026** | **AWS Free Tier Tasks** |
| **9** | - Thực hành **AWS Free Tier Task 2: Amazon Bedrock Playground**.<br>- Truy cập Amazon Bedrock và lựa chọn các Foundation Models.<br>- Tìm hiểu quy trình cung cấp thông tin Use Case.<br>- Tạo và chạy các câu lệnh prompt.<br>- Học cách gửi AWS Support Case khi quyền truy cập mô hình bị giới hạn. | **24/09/2026** | **24/09/2026** | **AWS Free Tier Tasks** |
| **10** | - Thực hành **AWS Free Tier Task 3: AWS Budgets**.<br>- Tạo ngân sách chi phí (Cost Budget).<br>- Cấu hình thông báo qua email để theo dõi chi phí.<br>- Hiểu tầm quan trọng của cảnh báo ngân sách (Budget Alerts) và quản lý chi phí. | **25/09/2026** | **25/09/2026** | **AWS Free Tier Tasks** |
| **11** | - Thực hành **AWS Free Tier Task 4: Create a Lambda Web App**.<br>- Tạo Lambda Function sử dụng Blueprint.<br>- Sử dụng template **Getting Started with Lambda HTTP**.<br>- Cấu hình Function URL.<br>- Kiểm tra Function và dọn dẹp tài nguyên Lambda. | **25/09/2026** | **25/09/2026** | **AWS Free Tier Tasks** |
| **12** | - Thực hành **AWS Free Tier Task 5: Create an Amazon RDS Database**.<br>- Tạo Managed Relational Database bằng tùy chọn Easy Create.<br>- Tìm hiểu về Aurora PostgreSQL Compatible.<br>- Chờ cơ sở dữ liệu chuyển sang trạng thái Available.<br>- Xóa database và DB Cluster sau khi hoàn thành bài lab. | **26/09/2026** | **26/09/2026** | **AWS Free Tier Tasks** |
| **13** | - Ôn lại việc sử dụng AWS Free Tier Credits và tối ưu hóa chi phí.<br>- Nhận diện các dịch vụ và cấu hình có thể tiêu tốn Credits nhanh chóng.<br>- Hiểu tầm quan trọng của việc giám sát và dọn dẹp tài nguyên AWS sau giờ thực hành.<br>- Đánh giá lại AWS Learning Roadmap và lập kế hoạch cho giai đoạn tiếp theo. | **26/09/2026** | **26/09/2026** | **AWS Free Tier 2025 Guide**<br>**Monitoring and Cost Optimization** |

---

## Kết quả đạt được trong Tuần 1:

* Nắm vững kiến thức nền tảng về **Điện toán đám mây** và các nhóm dịch vụ AWS chính:
  * Compute (Điện toán)
  * Storage (Lưu trữ)
  * Networking (Mạng)
  * Database (Cơ sở dữ liệu)
* Làm quen với chương trình **First Cloud Journey (FCAJ)**, các thành viên trong nhóm và các quy định thực tập.
* Tạo và bảo mật thành công tài khoản AWS với **xác thực hai yếu tố (MFA)** và cấu hình thanh toán.
* Sử dụng thành thạo **AWS Management Console** và biết cách định vị các dịch vụ quan trọng.
* Cài đặt và cấu hình thành công **AWS CLI** trên máy tính cá nhân.
* Thực hành thuần thục các lệnh AWS CLI cơ bản:
  * `aws --version`
  * `aws configure`
  * `aws configure list`
  * `aws sts get-caller-identity`
  * `aws ec2 describe-regions`
* Hiểu rõ các thành phần cốt lõi của **Amazon EC2**:
  * AMI
  * Instance Types
  * EBS
  * Security Groups
  * Key Pairs
  * Elastic IP
* Thực hành khởi tạo EC2 instance, kết nối qua **SSH**, quản lý ổ đĩa EBS và xóa tài nguyên sau khi sử dụng.
* Hiểu rõ chính sách **AWS Free Tier 2025** và cơ chế **$200 AWS Credit** cho các tài khoản tạo sau ngày 15/07/2025.
* Phân biệt được hai lựa chọn gói tài khoản:
  * Free Account Plan
  * Paid Account Plan
* Áp dụng thành công AWS Credits vào các bài thực hành thực tế.
* Hoàn thành bài lab **AWS Free Tier EC2 Task** (từ cấu hình, triển khai, kiểm thử đến dọn dẹp).
* Khám phá **Amazon Bedrock Playground** và làm việc với các Foundation Models cho các thử nghiệm AI/ML.
* Thực hành viết prompt và biết cách gửi **AWS Support Case** khi yêu cầu truy cập mô hình (Anthropic Claude) bị giới hạn.
* Cấu hình **AWS Budgets** thiết lập cảnh báo email để giám sát chi phí tự động.
* Phát triển ứng dụng **Serverless Web Application** sử dụng **AWS Lambda** và HTTP Blueprint.
* Khởi tạo và quản lý **Amazon RDS** database sử dụng **Aurora PostgreSQL Compatible**.
* Rèn luyện thói quen dọn dẹp tài nguyên nghiêm ngặt để tránh phát sinh chi phí ngoài ý muốn.
* Thành lập nhóm **4 thành viên** sẵn sàng cho các dự án AWS sắp tới.

---

## Kết quả học tập tổng thể:

Thông qua các hoạt động hoàn thành trong Tuần 1, tôi đã xây dựng được nền tảng vững chắc về **Điện toán đám mây AWS**, kết hợp giữa lý thuyết và kinh nghiệm thực hành thực tế.

Những kết quả học tập chính bao gồm:
* Nắm chắc các nguyên lý Điện toán đám mây và hệ sinh thái AWS.
* Hiểu rõ quy định, yêu cầu và lộ trình phát triển của chương trình FCAJ.
* Thành thạo thao tác trên AWS Management Console và giao diện AWS CLI.
* Có khả năng triển khai, kết nối và quản lý tài nguyên Amazon EC2 và EBS.
* Tối ưu hóa và sử dụng hiệu quả gói AWS Free Tier 2025 cùng khoản $200 Credit.
* Có kinh nghiệm thực tế với Serverless (Lambda), Cơ sở dữ liệu (RDS), AI/ML (Bedrock) và Quản lý chi phí (Budgets).
* Thiết lập được quy trình kiểm soát chi phí, thói quen dọn dẹp tài nguyên và kỹ năng làm việc nhóm hiệu quả.
