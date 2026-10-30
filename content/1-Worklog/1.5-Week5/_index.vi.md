
---
title: "1.5. Nhật ký công việc Tuần 5"
weight: 5
draft: false
---

## Mục tiêu Tuần 5

- Hiểu vai trò của hệ thống giám sát và ghi nhật ký tập trung trong môi trường AWS; tìm hiểu các chức năng chính của Amazon CloudWatch như Metrics, Logs, Alarms và Dashboards.
- Nắm được cách theo dõi hoạt động của EC2 thông qua các chỉ số hệ thống, nhận biết tình trạng sử dụng tài nguyên bất thường và thiết lập cảnh báo để phát hiện sớm các vấn đề về hạ tầng.
- Tìm hiểu cách tích hợp Amazon CloudWatch với Amazon Simple Notification Service (SNS) để tự động gửi thông báo qua email khi các chỉ số giám sát đạt đến ngưỡng cảnh báo.
- Khám phá AWS CloudTrail và hiểu cách dịch vụ này ghi nhận các hoạt động API, theo dõi thao tác của người dùng và hỗ trợ kiểm toán, quản trị bảo mật.
- Làm quen với các công cụ quản lý chi phí AWS như Cost Explorer và AWS Budgets, bao gồm phân tích chi phí theo dịch vụ và thiết lập cảnh báo ngân sách.
- Thực hành cài đặt và cấu hình CloudWatch Agent trên EC2 để thu thập các chỉ số Memory, Disk, chuyển tiếp nhật ký hệ thống và xây dựng Dashboard giám sát tập trung.

## Các công việc thực hiện trong tuần

| **Ngày** | **Công việc thực hiện** | **Ngày bắt đầu** | **Ngày hoàn thành** | **Tài liệu tham khảo** |
| :--- | :--- | :--- | :--- | :--- |
| Thứ Hai | - Tìm hiểu kiến trúc và các thành phần cơ bản của Amazon CloudWatch, bao gồm Metrics, Namespaces, Dimensions, Log Groups và Log Streams.<br>- Thực hành truy cập các chỉ số giám sát của EC2 để hiểu cách CloudWatch thu thập, lưu trữ và hiển thị thông tin về tài nguyên hệ thống.<br>- So sánh Basic Monitoring (chu kỳ 5 phút) và Detailed Monitoring (chu kỳ 1 phút), tìm hiểu sự khác biệt về tần suất giám sát và chi phí sử dụng.<br>- Phân tích các chỉ số quan trọng của EC2 như CPUUtilization, StatusCheckFailed, NetworkIn và NetworkOut nhằm nhận biết các dấu hiệu bất thường về hiệu suất. | 19/10/2026 | 19/10/2026 | [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html)<br>[CloudWatch Concepts](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html) |
| Thứ Ba | - Tìm hiểu mô hình truyền tải thông điệp Publish/Subscribe của Amazon SNS và cách SNS Topic phân phối thông báo đến các địa chỉ đăng ký nhận tin.<br>- Tạo SNS Topic với tên `CloudWatch-Alerts-Topic` và thiết lập Email Subscription; thực hiện xác nhận đăng ký thông qua email xác minh.<br>- Tạo CloudWatch Alarm để theo dõi mức sử dụng CPU của EC2 với ngưỡng cảnh báo 80% trong khoảng thời gian đánh giá được cấu hình.<br>- Kết nối Alarm với SNS Topic và kiểm tra quy trình gửi thông báo, qua đó hiểu cách AWS tự động gửi email khi trạng thái cảnh báo chuyển sang ALARM. | 20/10/2026 | 20/10/2026 | [Amazon SNS User Guide](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)<br>[CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) |
| Thứ Tư | - Tìm hiểu AWS CloudTrail và vai trò của dịch vụ trong việc ghi nhận hoạt động tài khoản, các yêu cầu API và những thay đổi được thực hiện trên tài nguyên AWS.<br>- Phân tích cấu trúc CloudTrail Events, tập trung vào các thông tin như User Identity, Event Time, Event Source, Source IP Address và Request Parameters.<br>- Thực hành kiểm tra lịch sử API thông qua CloudTrail Event History để xác định ai đã thực hiện thao tác, thời điểm thực hiện và dịch vụ AWS liên quan.<br>- Cấu hình Multi-region CloudTrail Trail để thu thập Management Events và chuyển các tệp nhật ký đến Amazon S3 nhằm phục vụ kiểm toán tập trung và lưu trữ lâu dài. | 21/10/2026 | 21/10/2026 | [AWS CloudTrail User Guide](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)<br>[CloudTrail Events](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html) |
| Thứ Năm | - Khám phá các công cụ AWS Cost Management và tìm hiểu cách theo dõi, kiểm soát chi phí phát sinh từ các dịch vụ AWS.<br>- Sử dụng AWS Cost Explorer để xem lịch sử chi tiêu, nhóm chi phí theo dịch vụ và khu vực, đồng thời xác định những tài nguyên có mức chi phí đáng kể trong hóa đơn hàng tháng.<br>- Thực hành tạo AWS Budget với giới hạn ngân sách hàng tháng và thiết lập thông báo khi chi phí thực tế hoặc chi phí dự báo đạt 80% ngân sách.<br>- Kiểm tra cơ chế cảnh báo ngân sách và tìm hiểu cách giám sát chi phí giúp hạn chế các khoản phí ngoài dự kiến từ EC2, RDS và NAT Gateway. | 22/10/2026 | 22/10/2026 | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-whatis.html)<br>[AWS Budgets Guide](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html) |
| Thứ Sáu | - **Thực hành và xây dựng hệ thống giám sát tập trung:**<br>- Cài đặt và cấu hình CloudWatch Agent trên máy chủ Linux EC2, chuẩn bị cấu hình Agent để thu thập thêm thông tin về tình trạng hoạt động của hệ thống.<br>- Kích hoạt thu thập các chỉ số Memory và Disk, là những thông tin không được cung cấp mặc định trong Basic Monitoring của EC2.<br>- Cấu hình Agent để thu thập các tệp nhật ký hệ thống như `/var/log/syslog` và chuyển dữ liệu nhật ký lên Log Group tương ứng trong CloudWatch Logs.<br>- Xây dựng CloudWatch Dashboard tùy chỉnh, hiển thị các chỉ số CPU, Memory, Disk, Network Traffic và số lượng kết nối RDS.<br>- Kiểm tra các thành phần trên Dashboard và xác nhận dữ liệu giám sát được gửi lên CloudWatch chính xác.<br>- Chụp ảnh màn hình các bước cấu hình, cảnh báo và Dashboard để lưu lại minh chứng cho quá trình thực hành. | 23/10/2026 | 23/10/2026 | [CloudWatch Agent Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html)<br>[CloudWatch Dashboards](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html) |

## Kết quả đạt được trong Tuần 5

- Nắm vững các chức năng chính của Amazon CloudWatch và hiểu được vai trò của dịch vụ trong việc giám sát hạ tầng tập trung, thu thập Metrics, quản lý Logs và phân tích hiệu suất hệ thống.
- Thực hành theo dõi hoạt động của EC2 thông qua các chỉ số quan trọng và hiểu rõ sự khác biệt giữa Basic Monitoring và Detailed Monitoring.
- Tạo thành công SNS Topic, cấu hình Email Subscription và tích hợp SNS với CloudWatch Alarms để tự động gửi thông báo khi hệ thống phát sinh cảnh báo.
- Thiết lập cảnh báo CPU Utilization với ngưỡng 80%, hiểu được cách CloudWatch đánh giá dữ liệu giám sát và kích hoạt thông báo khi mức sử dụng tài nguyên vượt ngưỡng quy định.
- Hiểu cách AWS CloudTrail ghi nhận lịch sử sự kiện API, theo dõi hoạt động người dùng và sử dụng Amazon S3 để lưu trữ dữ liệu phục vụ kiểm toán.
- Thực hành sử dụng AWS Cost Explorer để phân tích chi phí hạ tầng và cấu hình AWS Budgets nhằm theo dõi ngân sách hàng tháng, nhận thông báo khi chi tiêu đạt ngưỡng đã thiết lập.
- Cài đặt và cấu hình CloudWatch Agent trên EC2 để thu thập thêm các chỉ số Memory, Disk và chuyển tiếp nhật ký hệ thống lên CloudWatch Logs.
- Xây dựng CloudWatch Dashboard tập trung, hỗ trợ theo dõi tổng quan tình trạng hoạt động của hạ tầng, bao gồm EC2, RDS và lưu lượng mạng.
- Nâng cao khả năng phát hiện sự cố, theo dõi mức sử dụng tài nguyên, kiểm tra lịch sử hoạt động và kiểm soát chi phí vận hành thông qua các công cụ giám sát của AWS.
