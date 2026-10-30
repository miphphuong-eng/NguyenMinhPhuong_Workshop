---
title: "1.1. Nhật ký công việc Tuần 1"
weight: 1
draft: false
---

## Mục tiêu Tuần 1

- Làm quen với các thành viên trong chương trình First Cloud AI Journey (FCAJ).
- Tìm hiểu nội quy, yêu cầu và lộ trình thực tập kéo dài 13 tuần.
- Trang bị kiến thức nền tảng về Cloud Computing và Amazon Web Services (AWS).
- Tìm hiểu các nhóm dịch vụ cốt lõi của AWS:
  - Compute (Điện toán)
  - Storage (Lưu trữ)
  - Networking (Mạng)
  - Database (Cơ sở dữ liệu)
- Tạo và bảo mật tài khoản AWS, đồng thời tìm hiểu chương trình AWS Free Tier.
- Làm quen với AWS Management Console và AWS CLI.
- Tìm hiểu các khái niệm về Amazon EC2 và thực hành các bài lab EC2 cơ bản.
- Tìm hiểu chương trình AWS Free Tier 2025 và AWS Credits.
- Hoàn thành các bài thực hành với những dịch vụ AWS sau:
  - Amazon EC2
  - Amazon Bedrock
  - AWS Budgets
  - AWS Lambda
  - Amazon RDS
- Học cách giám sát tài nguyên AWS, kiểm soát chi phí và dọn dẹp các tài nguyên không còn sử dụng.
- Thành lập nhóm học tập và chuẩn bị cho các dự án AWS sắp tới.

---

## Hoạt động trong tuần

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| :---: | :--- | :---: | :---: | :--- |
| **Thứ 2** | - Tham gia buổi định hướng FCJ Workforce và làm quen với các thành viên trong nhóm.<br>- Tìm hiểu nội quy thực tập, hướng dẫn làm việc và lộ trình thực tập 13 tuần.<br>- Học các kiến thức cơ bản về Cloud Computing và các mô hình dịch vụ IaaS, PaaS, SaaS.<br>- Tìm hiểu cơ sở hạ tầng toàn cầu của AWS: Regions, Availability Zones và Edge Locations.<br>- Tìm hiểu mô hình Shared Responsibility Model của AWS. | 21/09/2026 | 21/09/2026 | [Nội quy FCAJ](https://hcm-rules.awsfcaj.com/1-regulations/)<br>[Tổng quan AWS Cloud](https://aws.amazon.com/what-is-aws/)<br>[Cơ sở hạ tầng toàn cầu AWS](https://aws.amazon.com/about-aws/global-infrastructure/)<br>[Mô hình trách nhiệm chung AWS](https://aws.amazon.com/compliance/shared-responsibility-model/) |
| **Thứ 3** | - Tìm hiểu các dịch vụ AWS cốt lõi: EC2, S3, VPC và RDS.<br>- Tạo và bảo mật tài khoản AWS, bật MFA và kiểm tra cài đặt thanh toán.<br>- Tìm hiểu các khái niệm AWS IAM, bao gồm IAM User, Group, Policy và Role.<br>- Thực hành tạo IAM User theo nguyên tắc Least Privilege (quyền tối thiểu cần thiết).<br>- Cài đặt AWS CLI v2 và cấu hình profile bằng lệnh `aws configure`. | 22/09/2026 | 22/09/2026 | [Các dịch vụ AWS](https://aws.amazon.com/products/)<br>[AWS Free Tier](https://aws.amazon.com/free/)<br>[Hướng dẫn AWS IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)<br>[Các phương pháp bảo mật IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)<br>[Hướng dẫn AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/) |
| **Thứ 4** | - Tìm hiểu các thành phần của Amazon EC2: AMI, Instance Types, EBS, Security Groups, Key Pairs và Elastic IP.<br>- **AWS Free Tier Task 1:** Khởi tạo và cấu hình một EC2 Instance.<br>- Thực hành kết nối đến EC2 thông qua SSH, gắn và quản lý EBS Volume.<br>- Kiểm tra trạng thái EC2 Instance và dọn dẹp các tài nguyên không còn sử dụng. | 23/09/2026 | 23/09/2026 | [Hướng dẫn Amazon EC2](https://docs.aws.amazon.com/ec2/)<br>[Hướng dẫn Amazon EBS](https://docs.aws.amazon.com/ebs/)<br>[AWS Free Tier](https://aws.amazon.com/free/) |
| **Thứ 5** | - Tìm hiểu chương trình AWS Free Tier 2025, AWS Credits (lên đến 200 USD đối với tài khoản đủ điều kiện) và sự khác biệt giữa Free Plan và Paid Plan.<br>- Ôn tập kết quả **Task 1: Amazon EC2**.<br>- Học cách theo dõi AWS Credits, mức sử dụng dịch vụ và chi phí thanh toán.<br>- **AWS Free Tier Task 2:** Sử dụng Amazon Bedrock Playground, khám phá Foundation Models và thực hành viết prompt. | 24/09/2026 | 24/09/2026 | [AWS Free Tier](https://aws.amazon.com/free/)<br>[AWS Billing](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)<br>[Hướng dẫn Amazon Bedrock](https://docs.aws.amazon.com/bedrock/) |
| **Thứ 6** | - **AWS Free Tier Task 3:** Tạo AWS Budget và cấu hình cảnh báo chi phí qua email.<br>- Tìm hiểu cách theo dõi ngân sách và kiểm soát chi tiêu AWS.<br>- **AWS Free Tier Task 4:** Xây dựng ứng dụng web sử dụng AWS Lambda và cấu hình Function URL.<br>- Thực hành triển khai, kiểm thử và quản lý Lambda Function. | 25/09/2026 | 25/09/2026 | [Hướng dẫn AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)<br>[Hướng dẫn AWS Lambda](https://docs.aws.amazon.com/lambda/) |
| **Thứ 7** | - **AWS Free Tier Task 5:** Tạo cơ sở dữ liệu Amazon RDS và tìm hiểu Aurora PostgreSQL.<br>- Tìm hiểu cách cấu hình cơ sở dữ liệu, kết nối và thực hiện các thao tác cơ bản trên RDS.<br>- Ôn tập kết quả của cả năm bài thực hành AWS Free Tier (Tasks 1–5).<br>- Kiểm tra AWS Billing, AWS Credits và các tài nguyên đang hoạt động để tránh phát sinh chi phí ngoài dự kiến.<br>- Dọn dẹp các tài nguyên không còn sử dụng và hoàn thiện Nhật ký công việc Tuần 1. | 26/09/2026 | 26/09/2026 | [Hướng dẫn Amazon RDS](https://docs.aws.amazon.com/rds/)<br>[Hướng dẫn Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/)<br>[AWS Cost Management](https://docs.aws.amazon.com/cost-management/) |

---

## Kết quả đạt được trong Tuần 1

- Nắm được kiến thức nền tảng về Cloud Computing và các nhóm dịch vụ chính của AWS.
- Làm quen với chương trình FCAJ, các thành viên trong nhóm và nội quy thực tập.
- Tạo và bảo mật tài khoản AWS bằng phương thức xác thực đa yếu tố (MFA).
- Làm quen với AWS Management Console và các dịch vụ AWS quan trọng.
- Cài đặt và cấu hình thành công AWS CLI trên máy tính cá nhân.
- Thực hành các lệnh AWS CLI cơ bản:
  - `aws --version`
  - `aws configure`
  - `aws configure list`
  - `aws sts get-caller-identity`
  - `aws ec2 describe-regions`
  - <img width="548" height="107" alt="image" src="https://github.com/user-attachments/assets/99bfbbe0-9e43-47b5-bc11-97932e1ef1db" />

- Hiểu được các thành phần chính của Amazon EC2: AMI, Instance Types, EBS, Security Groups, Key Pairs và Elastic IP.
- Thực hành khởi tạo EC2 Instance, kết nối thông qua SSH và quản lý EBS Volume.
- Tìm hiểu chương trình AWS Free Tier 2025 và AWS Credits dành cho các tài khoản đủ điều kiện.
- Phân biệt được Free Plan và Paid Plan.
- Khám phá Amazon Bedrock Playground, Foundation Models và kỹ thuật viết prompt.
- Thực hành tạo AWS Budgets và cấu hình cảnh báo chi phí qua email.
- Xây dựng ứng dụng web Serverless sử dụng AWS Lambda và Function URL.
- Tạo cơ sở dữ liệu Amazon RDS và tìm hiểu Aurora PostgreSQL.
- Nâng cao kỹ năng theo dõi chi phí AWS và dọn dẹp các tài nguyên không còn sử dụng.
- Hoàn thành các hoạt động thực hành AWS Free Tier Tasks 1–5.
- Thành lập nhóm học tập gồm 4 thành viên để chuẩn bị cho các dự án AWS sắp tới.

---
