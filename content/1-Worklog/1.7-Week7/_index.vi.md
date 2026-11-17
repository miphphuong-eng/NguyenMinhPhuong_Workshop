
---
title: "1.7. Nhật ký công việc Tuần 7"
weight: 7
draft: false
---

## Mục tiêu Tuần 7

- Tìm hiểu khái niệm và mục đích sử dụng VPC Endpoint trong AWS.
- Phân biệt Gateway Endpoint và Interface Endpoint.
- Tìm hiểu cách cấu hình Amazon S3 Gateway VPC Endpoint.
- Thực hành truy cập Amazon S3 một cách riêng tư từ EC2 trong Private Subnet mà không cần sử dụng Internet Gateway hoặc NAT Gateway.
- Kiểm tra kết nối thông qua AWS CLI và hiểu cách cấu hình định tuyến, bảo mật liên quan.
- Đánh giá lợi ích về chi phí khi sử dụng Gateway Endpoint thay vì định tuyến lưu lượng S3 qua NAT Gateway.

## Các công việc thực hiện trong tuần

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|---|---|---|---|---|
| Thứ Hai | Tìm hiểu khái niệm và mục đích sử dụng VPC Endpoint. Phân biệt Gateway Endpoint và Interface Endpoint. Tìm hiểu cách S3 Gateway Endpoint sử dụng AWS-managed Prefix List để định tuyến lưu lượng riêng tư thông qua mạng AWS. | 02/11/2026 | 02/11/2026 | [VPC Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints.html) |
| Thứ Ba | Ôn tập kiến trúc VPC hiện có, bao gồm Public Subnet và Private Subnet. Tìm hiểu cách EC2 trong Private Subnet truy cập các dịch vụ AWS mà không cần tuyến kết nối Internet trực tiếp. Kiểm tra EC2, IAM permissions, Security Groups và cấu hình AWS CLI trước khi tạo Endpoint. | 03/11/2026 | 03/11/2026 | [VPC Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) |
| Thứ Tư | Tạo Amazon S3 Gateway VPC Endpoint với service name `com.amazonaws.ap-southeast-1.s3`. Liên kết Endpoint với Route Table đang được sử dụng bởi Private Subnet. Kiểm tra tuyến đường được tự động thêm thông qua S3 Prefix List và VPC Endpoint ID. | 04/11/2026 | 04/11/2026 | [S3 VPC Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html) |
| Thứ Năm | Kiểm tra khả năng truy cập Amazon S3 riêng tư từ EC2 bằng các lệnh AWS CLI như `aws s3 ls` và `aws s3 cp`. Xác minh lưu lượng truy cập S3 được định tuyến thông qua Gateway Endpoint. Kiểm tra Endpoint Policy, IAM permissions và cấu hình mạng nếu xảy ra lỗi truy cập. Ghi lại kết quả kiểm thử và chụp ảnh minh chứng. | 05/11/2026 | 05/11/2026 | [AWS CLI S3 Commands](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/index.html) |
| Thứ Sáu | So sánh việc sử dụng S3 Gateway Endpoint với phương án định tuyến lưu lượng S3 qua NAT Gateway. Đánh giá cấu hình, kết quả kiểm tra kết nối và các yếu tố bảo mật. Tổng hợp ưu điểm, hạn chế của Gateway Endpoint và sắp xếp hình ảnh, ghi chú kỹ thuật để hoàn thiện báo cáo tuần. | 06/11/2026 | 06/11/2026 | [AWS PrivateLink Pricing](https://aws.amazon.com/privatelink/pricing/) |

## Kết quả đạt được trong Tuần 7

- Hiểu được mục đích sử dụng VPC Endpoint và sự khác nhau giữa Gateway Endpoint và Interface Endpoint.
- Biết cách tạo và cấu hình S3 Gateway VPC Endpoint.
- Hiểu cách Route Table sử dụng AWS-managed Prefix List để định tuyến lưu lượng S3 thông qua Endpoint.
- Thực hành truy cập Amazon S3 riêng tư từ EC2 trong Private Subnet bằng AWS CLI.
- Nâng cao hiểu biết về IAM permissions, Endpoint Policies và cấu hình mạng cần thiết để thiết lập kết nối riêng tư.
- Nhận biết lợi ích về chi phí khi sử dụng S3 Gateway Endpoint để tránh phí xử lý dữ liệu của NAT Gateway đối với lưu lượng S3 phù hợp.
