---
title: "1.1. Week 1 Worklog"
weight: 1
draft: false
---

## Mục tiêu Tuần 1

- Giao lưu và làm quen với các thành viên trong chương trình First Cloud AI Journey (FCAJ).
- Hiểu rõ các quy định, yêu cầu và lộ trình học tập của FCAJ.
- Nắm vững các khái niệm cơ bản về Điện toán đám mây (Cloud Computing) và Amazon Web Services (AWS).
- Tìm hiểu các nhóm dịch vụ cốt lõi của AWS:
  - Compute (Điện toán)
  - Storage (Lưu trữ)
  - Networking (Mạng)
  - Database (Cơ sở dữ liệu)
- Tạo và bảo mật tài khoản AWS, tìm hiểu các chính sách của gói AWS Free Tier.
- Học cách sử dụng giao diện quản trị AWS Management Console và giao diện dòng lệnh AWS CLI.
- Hiểu các khái niệm về Amazon EC2 và thực hành các bài lab EC2 cơ bản.
- Tìm hiểu về chương trình AWS Free Tier 2025 và khoản tín dụng **$200 AWS Credit**.
- Thực hành các bài tập thực tế với các dịch vụ AWS quan trọng, bao gồm:
  - Amazon EC2
  - Amazon Bedrock
  - AWS Budgets
  - AWS Lambda
  - Amazon RDS
- Học cách giám sát tài nguyên AWS, kiểm soát chi phí và dọn dẹp các tài nguyên không sử dụng.
- Thành lập nhóm học tập và chuẩn bị cho các dự án AWS tiếp theo.

---

## Các công việc thực hiện trong tuần

| Thứ | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :---: | :---: | :--- |
| **Thứ 2** | • Kết nối, làm quen với các thành viên FCAJ.<br>• Đọc và ghi chú nội quy, quy định thực tập. | 21/09/2026 | 21/09/2026 | [FCAJ Rules](https://hcm-rules.awsfcaj.com/) |
| **Thứ 3** | • Tạo & bảo mật tài khoản AWS Free Tier (bật MFA, cài đặt thanh toán).<br>• Làm quen AWS Console, cài đặt và cấu hình AWS CLI. | 22/09/2026 | 22/09/2026 | [What is AWS](https://aws.amazon.com/what-is-aws/)<br>[AWS Management Console](https://ap-southeast-2.console.aws.amazon.com/console/home?region=ap-southeast-2#) |
| **Thứ 4** | • Tìm hiểu tổng quan Điện toán đám mây & AWS.<br>• Khám phá các nhóm dịch vụ cốt lõi (Compute, Storage, Networking, Database). | 23/09/2026 | 23/09/2026 | [AWS IAM Introduction](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| **Thứ 5** | • Tìm hiểu khái niệm Amazon EC2 (AMI, EBS, Security Groups, Key Pairs).<br>• Thực hành khởi chạy EC2, kết nối SSH và quản lý EBS.<br>• Thực hành **Task 3** (Budgets), **Task 4** (Lambda App) & **Task 5** (RDS).<br>• Ôn tập tối ưu chi phí, giám sát và dọn dẹp tài nguyên. | 24/09/2026 | 24/09/2026 | [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |
| **Thứ 6** | • Tải và cài đặt công cụ AWS CLI v2 trên máy tính cá nhân.<br>• Khởi tạo profile mặc định qua lệnh `aws configure` (nhập Access Key, Secret Key, Default Region).<br>• Chạy thử nghiệm các câu lệnh CLI kiểm tra xác thực (`aws sts get-caller-identity`, `aws ec2 describe-regions`). | 25/09/2026 | 25/09/2026 | [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html) |

---

## Kết quả đạt được trong Tuần 1

- Nắm vững kiến thức nền tảng về **Điện toán đám mây** và các nhóm dịch vụ AWS chính:
  - Compute (Điện toán)
  - Storage (Lưu trữ)
  - Networking (Mạng)
  - Database (Cơ sở dữ liệu)
- Làm quen với chương trình **First Cloud Journey (FCAJ)**, các thành viên trong nhóm và các quy định thực tập.
- Tạo và bảo mật thành công tài khoản AWS với **xác thực hai yếu tố (MFA)** và cấu hình thanh toán.
- Sử dụng thành thạo **AWS Management Console** và biết cách định vị các dịch vụ quan trọng.
- Cài đặt và cấu hình thành công **AWS CLI** trên máy tính cá nhân.
- Thực hành thuần thục các lệnh AWS CLI cơ bản:
  - `aws --version`
  - `aws configure`
  - `aws configure list`
  - `aws sts get-caller-identity`
  - `aws ec2 describe-regions`
- Hiểu rõ các thành phần cốt lõi của **Amazon EC2**:
  - AMI
  - Instance Types
  - EBS
  - Security Groups
  - Key Pairs
  - Elastic IP
- Thực hành khởi tạo EC2 instance, kết nối qua **SSH**, quản lý ổ đĩa EBS và xóa tài nguyên sau khi sử dụng.
- Hiểu rõ chính sách **AWS Free Tier 2025** và cơ chế **$200 AWS Credit** cho các tài khoản tạo sau ngày 15/07/2025.
- Phân biệt được hai lựa chọn gói tài khoản:
  - Free Account Plan
  - Paid Account Plan
- Áp dụng thành công AWS Credits vào các bài thực hành thực tế.
- Hoàn thành bài lab **AWS Free Tier EC2 Task** (từ cấu hình, triển khai, kiểm thử đến dọn dẹp).
- Khám phá **Amazon Bedrock Playground** và làm việc với các Foundation Models cho các thử nghiệm AI/ML.
- Thực hành viết prompt và biết cách gửi **AWS Support Case** khi yêu cầu truy cập mô hình (Anthropic Claude) bị giới hạn.
- Cấu hình **AWS Budgets** thiết lập cảnh báo email để giám sát chi phí tự động.
- Phát triển ứng dụng **Serverless Web Application** sử dụng **AWS Lambda** và HTTP Blueprint.
- Khởi tạo và quản lý **Amazon RDS** database sử dụng **Aurora PostgreSQL Compatible**.
- Rèn luyện thói quen dọn dẹp tài nguyên nghiêm ngặt để tránh phát sinh chi phí ngoài ý muốn.
- Thành lập nhóm **4 thành viên** sẵn sàng cho các dự án AWS sắp tới.

---

## Kết quả học tập tổng thể

Thông qua các hoạt động hoàn thành trong Tuần 1, tôi đã xây dựng được nền tảng vững chắc về **Điện toán đám mây AWS**, kết hợp giữa lý thuyết và kinh nghiệm thực hành thực tế.

Những kết quả học tập chính bao gồm:
- Nắm chắc các nguyên lý Điện toán đám mây và hệ sinh thái AWS.
- Hiểu rõ quy định, yêu cầu và lộ trình phát triển của chương trình FCAJ.
- Thành thạo thao tác trên AWS Management Console và giao diện AWS CLI.
- Có khả năng triển khai, kết nối và quản lý tài nguyên Amazon EC2 và EBS.
- Tối ưu hóa và sử dụng hiệu quả gói AWS Free Tier 2025 cùng khoản $200 Credit.
- Có kinh nghiệm thực tế với Serverless (Lambda), Cơ sở dữ liệu (RDS), AI/ML (Bedrock) và Quản lý chi phí (Budgets).
- Thiết lập được quy trình kiểm soát chi phí, thói quen dọn dẹp tài nguyên và kỹ năng làm việc nhóm hiệu quả.
