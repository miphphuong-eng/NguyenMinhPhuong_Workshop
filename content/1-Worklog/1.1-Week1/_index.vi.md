---
title: "1.1. Nhật ký công việc Tuần 1"
weight: 1
draft: false
---

## Mục tiêu Tuần 1

- Làm quen với các thành viên trong chương trình First Cloud AI Journey (FCAJ).
- Tìm hiểu các quy định, yêu cầu và lộ trình thực tập 13 tuần.
- Nắm vững kiến thức cơ bản về Điện toán đám mây (Cloud Computing) và Amazon Web Services (AWS).
- Tìm hiểu các nhóm dịch vụ cốt lõi của AWS:
  - Compute (Điện toán)
  - Storage (Lưu trữ)
  - Networking (Mạng)
  - Database (Cơ sở dữ liệu)
- Khởi tạo và bảo mật tài khoản AWS, tìm hiểu chương trình AWS Free Tier.
- Làm quen với AWS Management Console và AWS CLI.
- Tìm hiểu Amazon EC2 và thực hành các bài lab cơ bản.
- Tìm hiểu chương trình AWS Free Tier 2025 và AWS Credits.
- Thực hành các bài tập với các dịch vụ AWS:
  - Amazon EC2
  - Amazon Bedrock
  - AWS Budgets
  - AWS Lambda
  - Amazon RDS
- Học cách giám sát tài nguyên AWS, kiểm soát chi phí và dọn dẹp tài nguyên không sử dụng.
- Thành lập nhóm học tập và chuẩn bị cho các dự án AWS tiếp theo.

---

## Các công việc thực hiện trong tuần

| Thứ | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :---: | :--- | :---: | :---: | :--- |
| **Thứ 2** | - Tham gia buổi định hướng chương trình FCJ Workforce và làm quen với các thành viên trong nhóm.<br>- Tìm hiểu nội quy, quy định làm việc và lộ trình thực tập 13 tuần.<br>- Nghiên cứu khái niệm Điện toán đám mây (Cloud Computing) và các mô hình dịch vụ IaaS, PaaS, SaaS.<br>- Tìm hiểu cấu trúc hạ tầng toàn cầu AWS: Regions, Availability Zones và Edge Locations.<br>- Nghiên cứu mô hình trách nhiệm chung AWS (Shared Responsibility Model). | 21/09/2026 | 21/09/2026 | [Nội quy FCJ](https://hcm-rules.awsfcaj.com/1-regulations/)<br>[Tổng quan AWS](https://aws.amazon.com/what-is-aws/)<br>[Hạ tầng toàn cầu AWS](https://aws.amazon.com/about-aws/global-infrastructure/)<br>[Mô hình trách nhiệm chung](https://aws.amazon.com/compliance/shared-responsibility-model/) |
| **Thứ 3** | - Tìm hiểu các dịch vụ cốt lõi của AWS: EC2, S3, VPC và RDS.<br>- Khởi tạo và bảo mật tài khoản AWS, kích hoạt MFA và kiểm tra thiết lập thanh toán.<br>- Tìm hiểu dịch vụ AWS IAM, bao gồm IAM User, Group, Policy và Role.<br>- Thực hành tạo IAM User theo nguyên tắc Least Privilege (quyền hạn tối thiểu).<br>- Cài đặt AWS CLI v2 và cấu hình profile bằng lệnh `aws configure`. | 22/09/2026 | 22/09/2026 | [Các dịch vụ AWS](https://aws.amazon.com/products/)<br>[AWS Free Tier](https://aws.amazon.com/free/)<br>[AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)<br>[IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)<br>[AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/) |
| **Thứ 4** | - Tìm hiểu các thành phần của Amazon EC2: AMI, Instance Types, EBS, Security Groups, Key Pairs và Elastic IP.<br>- **AWS Free Tier Task 1:** Khởi tạo và cấu hình EC2 Instance.<br>- Thực hành kết nối EC2 thông qua SSH và tìm hiểu cách gắn, quản lý ổ đĩa EBS.<br>- Kiểm tra trạng thái EC2 và thực hành dọn dẹp các tài nguyên không còn sử dụng. | 23/09/2026 | 23/09/2026 | [Amazon EC2 Guide](https://docs.aws.amazon.com/ec2/)<br>[Amazon EBS Guide](https://docs.aws.amazon.com/ebs/)<br>[AWS Free Tier](https://aws.amazon.com/free/) |
| **Thứ 5** | - Tìm hiểu chương trình AWS Free Tier 2025, hệ thống AWS Credits (tối đa 200 USD đối với tài khoản đủ điều kiện) và sự khác biệt giữa Free Plan và Paid Plan.<br>- Kiểm tra kết quả thực hành **Task 1: Amazon EC2**.<br>- Tìm hiểu cách theo dõi AWS Credits, mức sử dụng dịch vụ và chi phí thanh toán.<br>- **AWS Free Tier Task 2:** Sử dụng Amazon Bedrock Playground, lựa chọn Foundation Models và thử nghiệm các câu lệnh Prompt. | 24/09/2026 | 24/09/2026 | [AWS Free Tier](https://aws.amazon.com/free/)<br>[AWS Billing](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)<br>[Amazon Bedrock Guide](https://docs.aws.amazon.com/bedrock/) |
| **Thứ 6** | - **AWS Free Tier Task 3:** Tạo ngân sách AWS Budgets và thiết lập cảnh báo chi phí qua email.<br>- Tìm hiểu cách theo dõi ngân sách và kiểm soát chi tiêu AWS.<br>- **AWS Free Tier Task 4:** Xây dựng ứng dụng web bằng AWS Lambda và cấu hình Function URL.<br>- Thực hành triển khai, kiểm tra và quản lý Lambda Function. | 25/09/2026 | 25/09/2026 | [AWS Budgets Guide](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)<br>[AWS Lambda Guide](https://docs.aws.amazon.com/lambda/) |
| **Thứ 7** | - **AWS Free Tier Task 5:** Tạo cơ sở dữ liệu Amazon RDS và tìm hiểu Aurora PostgreSQL.<br>- Tìm hiểu cách cấu hình cơ sở dữ liệu, kết nối và kiểm tra hoạt động của RDS.<br>- Tổng hợp kết quả thực hành 5 bài AWS Free Tier Task 1–5.<br>- Kiểm tra AWS Billing, AWS Credits và các tài nguyên đang hoạt động để tránh phát sinh chi phí ngoài dự kiến.<br>- Dọn dẹp tài nguyên không còn sử dụng và hoàn thiện Worklog Tuần 1. | 26/09/2026 | 26/09/2026 | [Amazon RDS Guide](https://docs.aws.amazon.com/rds/)<br>[Amazon Aurora Guide](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/)<br>[AWS Cost Management](https://docs.aws.amazon.com/cost-management/) |

---

## Kết quả đạt được trong Tuần 1

- Nắm được kiến thức nền tảng về Điện toán đám mây và các nhóm dịch vụ AWS chính.
- Làm quen với chương trình FCAJ, các thành viên trong nhóm và quy định thực tập.
- Khởi tạo và bảo mật tài khoản AWS bằng Multi-Factor Authentication (MFA).
- Làm quen với AWS Management Console và các dịch vụ quan trọng.
- Cài đặt và cấu hình thành công AWS CLI trên máy tính cá nhân.
- Thực hành các lệnh AWS CLI cơ bản:
  - `aws --version`
  - `aws configure`
  - `aws configure list`
  - `aws sts get-caller-identity`
  - `aws ec2 describe-regions`
- Hiểu các thành phần chính của Amazon EC2: AMI, Instance Types, EBS, Security Groups, Key Pairs và Elastic IP.
- Thực hành khởi tạo EC2 Instance, kết nối SSH và quản lý ổ đĩa EBS.
- Tìm hiểu chương trình AWS Free Tier 2025 và AWS Credits dành cho tài khoản đủ điều kiện.
- Phân biệt Free Plan và Paid Plan.
- Khám phá Amazon Bedrock Playground, Foundation Models và thực hành viết Prompt.
- Thực hành tạo AWS Budgets và thiết lập cảnh báo chi phí qua email.
- Xây dựng ứng dụng web Serverless bằng AWS Lambda và Function URL.
- Tạo cơ sở dữ liệu Amazon RDS và tìm hiểu Aurora PostgreSQL.
- Nâng cao kỹ năng giám sát chi phí và dọn dẹp tài nguyên AWS.
- Hoàn thành các nội dung thực hành AWS Free Tier Task 1–5.
- Thành lập nhóm học tập gồm 4 thành viên để chuẩn bị cho các dự án AWS tiếp theo.

---

## Kết quả học tập tổng thể

Thông qua các hoạt động trong Tuần 1, tôi đã xây dựng được nền tảng kiến thức về Điện toán đám mây AWS, kết hợp giữa lý thuyết và thực hành.

Những kết quả học tập chính bao gồm:

- Hiểu các nguyên lý cơ bản của Điện toán đám mây và hệ sinh thái AWS.
- Nắm được quy định, yêu cầu và lộ trình thực tập của chương trình FCAJ.
- Biết cách sử dụng AWS Management Console và AWS CLI.
- Có khả năng khởi tạo, kết nối và quản lý tài nguyên Amazon EC2 và EBS.
- Hiểu chương trình AWS Free Tier 2025 và cơ chế AWS Credits.
- Có kinh nghiệm thực hành với các dịch vụ Serverless (Lambda), Cơ sở dữ liệu (RDS), AI/ML (Bedrock) và Quản lý chi phí (Budgets).
- Hình thành thói quen giám sát tài nguyên, kiểm soát chi phí và dọn dẹp các dịch vụ AWS không còn sử dụng.
- Phát triển kỹ năng tự học và làm việc nhóm để chuẩn bị cho các dự án tiếp theo.
