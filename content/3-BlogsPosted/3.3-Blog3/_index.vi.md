---
title: "Blog 3"
date: 2026-11-24
weight: 3
chapter: false
pre: "<b> 3.3. </b>"
---

# AMAZON EVENTBRIDGE SCHEDULER – MỘT DỊCH VỤ NHỎ NHƯNG CÓ VÕ KHI XÂY DỰNG PROJECT TRÊN AWS

Trong quá trình phát triển một ứng dụng, có rất nhiều công việc không cần thực hiện ngay lập tức mà phải chạy theo một lịch trình nhất định. Ví dụ như gửi email nhắc lịch hẹn, tự động cập nhật dữ liệu mỗi 30 phút, xóa các bản ghi hết hạn hoặc kiểm tra trạng thái hệ thống vào cuối ngày.

Nếu sử dụng một máy chủ EC2 để xử lý những công việc này, chúng ta cần duy trì máy chủ, cấu hình môi trường và tự quản lý lịch chạy. Điều này có thể gây lãng phí tài nguyên nếu tác vụ chỉ cần thực hiện trong vài giây.

Để giải quyết vấn đề này, Amazon Web Services cung cấp **Amazon EventBridge Scheduler** – một dịch vụ lập lịch Serverless cho phép tự động kích hoạt các dịch vụ AWS theo thời gian định trước mà không cần quản lý máy chủ riêng.

Trong bài viết này, chúng ta sẽ tìm hiểu cách EventBridge Scheduler hoạt động, các kiểu lập lịch, những tính năng nổi bật và cách ứng dụng dịch vụ này để tự động gọi AWS Lambda trong một project thực tế.

### 1. Amazon EventBridge Scheduler là gì?

Amazon EventBridge Scheduler là dịch vụ lập lịch được quản lý bởi AWS, cho phép người dùng tạo và quản lý các tác vụ chạy tại một thời điểm cụ thể hoặc lặp lại theo chu kỳ.

Thay vì phải viết chương trình liên tục kiểm tra thời gian rồi gọi API, chúng ta chỉ cần tạo một Schedule, xác định thời gian thực thi và lựa chọn dịch vụ đích (Target). EventBridge Scheduler sẽ tự động gửi yêu cầu đến dịch vụ đó khi đến thời điểm đã cấu hình.

Một số dịch vụ có thể được kích hoạt thông qua EventBridge Scheduler:

- **AWS Lambda:** Thực thi các đoạn code xử lý dữ liệu hoặc logic nghiệp vụ.
- **Amazon ECS / AWS Fargate:** Khởi chạy container để thực hiện các tác vụ cần nhiều tài nguyên hơn.
- **AWS Step Functions:** Kích hoạt một quy trình gồm nhiều bước xử lý.
- **Amazon SNS:** Gửi thông báo đến các subscriber.
- **Amazon SQS:** Đưa message vào hàng đợi để hệ thống xử lý sau.
- **Amazon EventBridge Event Bus:** Phát sự kiện để các thành phần khác trong hệ thống tiếp nhận.

Với Universal Target, EventBridge Scheduler có thể gọi hơn 6.000 API operations thuộc hơn 270 dịch vụ AWS. Điều này giúp Scheduler tích hợp linh hoạt với nhiều thành phần trong kiến trúc Cloud.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/eventbridge-scheduler-architecture.png" alt="Amazon EventBridge Scheduler architecture" style="width: 90%; max-width: 850
