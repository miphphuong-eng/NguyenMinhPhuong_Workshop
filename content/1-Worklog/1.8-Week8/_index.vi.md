
---
title: "1.8. Nhật ký công việc Tuần 8"
weight: 8
draft: false
---

## Mục tiêu Tuần 8

- Tìm hiểu AWS PrivateLink và cách Interface VPC Endpoint thiết lập kết nối riêng tư đến các dịch vụ AWS.
- Thực hành cấu hình Interface VPC Endpoint cho Amazon S3 nhằm hỗ trợ kết nối Hybrid Access từ môi trường On-premises.
- Hiểu vai trò của Elastic Network Interfaces (ENIs), địa chỉ IP riêng, Security Groups và Private DNS.
- Áp dụng VPC Endpoint Policies để kiểm soát quyền truy cập vào tài nguyên Amazon S3.
- Viết và kiểm thử JSON Endpoint Policy nhằm giới hạn quyền truy cập vào các S3 Bucket được cho phép.
- Thực hiện dọn dẹp tài nguyên và kiểm tra chi phí AWS sau khi hoàn thành các bài thực hành.

## Các công việc thực hiện trong tuần

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|---|---|---|---|---|
| Thứ Hai | Tìm hiểu AWS PrivateLink và kiến trúc Interface VPC Endpoint. Nghiên cứu cách Interface Endpoint tạo Elastic Network Interface (ENI) với địa chỉ IP riêng bên trong các Subnet được lựa chọn. Tìm hiểu vai trò của Private DNS trong việc đơn giản hóa quá trình truy cập dịch vụ. So sánh Gateway Endpoint và Interface Endpoint, tập trung vào khả năng kết nối môi trường On-premises với AWS thông qua VPN hoặc Direct Connect. | 09/11/2026 | 09/11/2026 | [AWS PrivateLink Concepts](https://docs.aws.amazon.com/vpc/latest/privatelink/concepts.html) <br> [Amazon S3 Interface Endpoints](https://docs.aws.amazon.com/AmazonS3/latest/userguide/privatelink-interface-endpoints.html) |
| Thứ Ba | Tạo Interface VPC Endpoint cho Amazon S3 thông qua AWS Management Console. Lựa chọn VPC và Subnet phù hợp, cấu hình Security Group cho phép lưu lượng HTTPS qua cổng 443 từ các dải CIDR nguồn cần thiết và kiểm tra cấu hình DNS của Endpoint. Sử dụng `nslookup` hoặc `dig` để kiểm tra quá trình phân giải DNS và xác định các địa chỉ IP riêng của Endpoint. | 10/11/2026 | 10/11/2026 | [Interface VPC Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpce-interface-endpoints.html) |
| Thứ Tư | Tìm hiểu VPC Endpoint Policies và mối quan hệ giữa IAM Policies, S3 Bucket Policies và Endpoint Policies. Tạo JSON Endpoint Policy tùy chỉnh để chỉ cho phép truy cập các S3 Bucket của công ty đã được phê duyệt cùng những hành động cụ thể. Kiểm tra cách Policy kiểm soát các yêu cầu đi qua Endpoint và tìm hiểu nguyên tắc cấp quyền tối thiểu (Least Privilege). | 11/11/2026 | 11/11/2026 | [VPC Endpoint Policies](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) |
| Thứ Năm | Kiểm thử Endpoint Policy bằng AWS CLI. Thử truy cập Bucket công ty được cho phép bằng lệnh `aws s3 ls s3://allowed-company-bucket` và xác minh yêu cầu thành công khi đã cấu hình đầy đủ các quyền cần thiết. Tiếp tục thử truy cập Bucket bên ngoài hoặc không được cấp quyền bằng lệnh `aws s3 ls s3://external-personal-bucket` và kiểm tra yêu cầu bị Endpoint Policy từ chối. Ghi lại kết quả và đánh giá cách Endpoint Policy giúp giảm nguy cơ truyền dữ liệu trái phép. | 12/11/2026 | 12/11/2026 | [VPC Endpoint Policies](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) <br> [Preventing Data Exfiltration](https://aws.amazon.com/blogs/security/how-to-use-vpc-endpoint-policies-to-prevent-data-exfiltration/) |
| Thứ Sáu | Thực hiện dọn dẹp tài nguyên sau khi hoàn thành các bài thực hành. Xóa Interface VPC Endpoint và kiểm tra các Network Interface liên quan đến Endpoint được hệ thống tự động xóa. Terminate các EC2 thử nghiệm và xóa S3 Bucket thử nghiệm sau khi xác nhận không còn nhu cầu sử dụng và Bucket đã được làm trống. Kiểm tra AWS Billing và Cost Explorer để rà soát chi phí hoặc tài nguyên còn tồn tại. Tổng hợp các file cấu hình, ví dụ JSON Policy, ảnh chụp màn hình và ghi chú kỹ thuật để hoàn thiện tài liệu Chapter 5. | 13/11/2026 | 13/11/2026 | [AWS PrivateLink Pricing](https://aws.amazon.com/privatelink/pricing/) <br> [AWS Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html) |
| Thứ Bảy | Tham gia sự kiện Cloud Mastery do Trường Đại học FPT tổ chức. Tham dự các hoạt động và tìm hiểu thêm về các chủ đề liên quan đến Cloud Computing, công nghệ AWS và ứng dụng thực tế của điện toán đám mây. Tiếp thu thêm kiến thức thông qua những chia sẻ và trao đổi với các thành viên tham gia sự kiện. | 14/11/2026 | 14/11/2026 | Trường Đại học FPT – Sự kiện Cloud Mastery |

## Kết quả đạt được trong Tuần 8

- Hiểu được AWS PrivateLink và kiến trúc hoạt động của Interface VPC Endpoint.
- Nắm được cách Interface Endpoint sử dụng ENI, địa chỉ IP riêng và Private DNS để thiết lập kết nối riêng tư đến các dịch vụ AWS.
- Hiểu cách Interface VPC Endpoint hỗ trợ kết nối Hybrid Access đến Amazon S3 từ môi trường On-premises thông qua VPN hoặc Direct Connect.
- Thực hành tạo S3 Interface VPC Endpoint và cấu hình Security Groups, DNS.
- Xây dựng JSON VPC Endpoint Policies tùy chỉnh để giới hạn quyền truy cập vào các S3 Bucket được phê duyệt và những hành động được cho phép.
- Kiểm thử quyền truy cập S3 hợp lệ và không hợp lệ bằng AWS CLI, hiểu cách Endpoint Policy hỗ trợ ngăn chặn truyền dữ liệu không mong muốn.
- Thực hành dọn dẹp tài nguyên AWS và kiểm tra thông tin thanh toán nhằm hạn chế chi phí Cloud không cần thiết.
- Tham gia sự kiện Cloud Mastery do Trường Đại học FPT tổ chức, có thêm cơ hội tiếp cận các công nghệ điện toán đám mây và học hỏi kinh nghiệm thông qua các hoạt động tại sự kiện.
- Tổng hợp ghi chú kỹ thuật, ví dụ cấu hình và ảnh minh chứng để hoàn thiện báo cáo Chapter 5.
