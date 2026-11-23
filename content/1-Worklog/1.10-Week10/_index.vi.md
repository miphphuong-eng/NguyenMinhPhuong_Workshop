
---
title: "Nhật ký công việc Tuần 10"
date: 2026-11-23
weight: 10
chapter: false
pre: "<b> 1.10. </b>"
---

# Nhật ký công việc Tuần 10

### Mục tiêu tuần 10

- Cấu hình AWS IoT Core Topic Rules để tự động lưu trữ dữ liệu telemetry từ các thiết bị Edge vào Amazon S3 Raw Data Lake Buckets.
- Xây dựng các hàm AWS Lambda bằng Python/Node.js để xử lý logic Backend và thiết lập các RESTful API endpoints bằng Amazon API Gateway.
- Cấu hình AWS Glue Crawlers để tự động thu thập và lập danh mục Schema từ S3, đồng thời tạo Glue ETL Jobs để chuyển đổi dữ liệu thô sang định dạng Parquet phục vụ phân tích.
- Triển khai Web Dashboard sử dụng Next.js lên AWS Amplify và tích hợp Amazon Cognito User Pools để xác thực tài khoản nhà nghiên cứu.
- Nghiên cứu kiến trúc Cloud có khả năng mở rộng (Amazon ECS Fargate, ALB, Aurora Serverless v2 và ElastiCache) để chuẩn bị nội dung cho các bài viết kỹ thuật.

### Các công việc đã thực hiện trong tuần

| **Ngày** | **Công việc thực hiện** | **Ngày bắt đầu** | **Ngày hoàn thành** | **Tài liệu tham khảo** |
| :--- | :--- | :--- | :--- | :--- |
| Thứ Hai | - Cấu hình AWS IoT Core Rule để đăng ký nhận dữ liệu từ topic `lab/weather/telemetry`.<br>- Thiết lập S3 Action để ghi trực tiếp dữ liệu JSON vào Amazon S3 Raw Bucket, phân chia theo cấu trúc `year=YYYY/month=MM/day=DD/`.<br>- Kiểm tra bằng cách gửi các MQTT messages mô phỏng và xác minh việc tạo Object tự động trên S3. | 23/11/2026 | 23/11/2026 | [AWS IoT S3 Action](https://docs.aws.amazon.com/iot/latest/developerguide/s3-rule-action.html)<br>[AWS IoT Rule Tutorial](https://docs.aws.amazon.com/iot/latest/developerguide/iot-write-to-s3.html) |
| Thứ Ba | - Phát triển AWS Lambda Function để truy vấn dữ liệu telemetry thời tiết mới nhất.<br>- Tạo Amazon API Gateway REST API tích hợp với Lambda thông qua phương thức GET `/api/weather/latest`.<br>- Cấu hình CORS headers và kiểm tra phản hồi của API bằng Postman. | 24/11/2026 | 24/11/2026 | [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)<br>[API Gateway Integration](https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-with-lambda-integrations.html) |
| Thứ Tư | - Tạo AWS Glue Crawler để kiểm tra S3 Raw Bucket và trích xuất thông tin Schema vào AWS Glue Data Catalog.<br>- Phát triển Glue ETL Job sử dụng PySpark để lọc dữ liệu telemetry nhiễu và xuất dữ liệu sang S3 Processed Bucket dưới định dạng Parquet có nén.<br>- Chạy Glue Job và kiểm tra các tập dữ liệu đã được chuyển đổi trên S3. | 25/11/2026 | 25/11/2026 | [AWS Glue Crawlers](https://docs.aws.amazon.com/glue/latest/dg/add-crawler.html)<br>[AWS Glue ETL Jobs](https://docs.aws.amazon.com/glue/latest/dg/author-job.html) |
| Thứ Năm | - Tạo Amazon Cognito User Pool với tên `WeatherLabUserPool` và cấu hình thông tin xác thực App Client.<br>- Triển khai Next.js Web Dashboard lên AWS Amplify thông qua tích hợp Git Repository.<br>- Tích hợp Amplify Auth SDK vào giao diện Next.js để bảo vệ các trang giám sát thời tiết. | 26/11/2026 | 26/11/2026 | [AWS Amplify Hosting](https://docs.aws.amazon.com/amplify/latest/userguide/welcome.html)<br>[Amplify Authentication](https://docs.amplify.aws/lib/auth/getting-started/q/platform/js/) |
| Thứ Sáu | - **Nghiên cứu và thực hành Lab về kiến trúc Web Application có khả năng mở rộng:**<br>- Phân tích các thách thức về khả năng mở rộng của hệ thống thương mại điện tử có lưu lượng truy cập lớn.<br>- Nghiên cứu và thực hành kiểm tra luồng lưu lượng đầu cuối: Route 53 → CloudFront → AWS WAF → ALB → Amazon ECS Fargate → ElastiCache → Aurora Serverless v2.<br>- Thu thập tài liệu hướng dẫn kiến trúc từ AWS Solutions Guidance để chuẩn bị nội dung cho Technical Blog 1. | 27/11/2026 | 27/11/2026 | [AWS Web Store Guidance](https://docs.aws.amazon.com/solutions/web-store-on-aws/)<br>[Amazon ECS Fargate](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html) |

### Kết quả đạt được trong tuần 10

- Cấu hình AWS IoT Core Rules để tự động thu thập dữ liệu MQTT telemetry và lưu trữ các JSON Objects được phân vùng trên Amazon S3.
- Phát triển logic Backend bằng AWS Lambda và thiết lập các API endpoints thông qua Amazon API Gateway để cung cấp dữ liệu thời tiết cho Web Clients.
- Triển khai AWS Glue Crawlers và Glue ETL Jobs để chuyển đổi dữ liệu IoT thô thành các tệp Parquet được tối ưu cho việc phân tích và lưu trữ trên S3.
- Triển khai ứng dụng Frontend Next.js trên AWS Amplify và tích hợp Amazon Cognito User Pools để xác thực người dùng.
- Nâng cao kiến thức về kiến trúc Cloud quy mô doanh nghiệp, bao gồm Amazon ECS Fargate, Application Load Balancer (ALB), Aurora Serverless v2 và ElastiCache.
- Chuẩn bị sơ đồ kiến trúc và tài liệu kỹ thuật cho Technical Blog 1 với chủ đề: **Scalable E-Commerce Architecture (Kiến trúc thương mại điện tử có khả năng mở rộng)**.
