
---
title: "1.9. Nhật ký công việc Tuần 9"
weight: 9
draft: false
---

## Mục tiêu Tuần 9

- Phân tích yêu cầu dự án và xây dựng bản đề xuất nhóm cho đề tài "IoT Weather Platform for Lab Research", phục vụ hoạt động nghiên cứu của nhóm ITea Lab.
- Xác định phạm vi, mục tiêu và đối tượng sử dụng của dự án, với quy mô triển khai ban đầu gồm 5 trạm thời tiết sử dụng Raspberry Pi và ESP32, có khả năng mở rộng lên 15 trạm.
- Thiết kế kiến trúc AWS Serverless thống nhất sử dụng AWS IoT Core, AWS Lambda, Amazon S3, AWS Glue, API Gateway, AWS Amplify và Amazon Cognito.
- Xây dựng luồng thu thập dữ liệu cảm biến (Telemetry) thông qua giao thức MQTT giữa các thiết bị Edge và nền tảng AWS Cloud.
- Thiết kế sơ đồ kiến trúc tổng thể, bao gồm Edge Architecture và Platform Architecture.
- Ước tính chi phí vận hành hàng tháng bằng AWS Pricing Calculator và xác định các rủi ro kỹ thuật, tài chính cùng phương án giảm thiểu.

## Các công việc thực hiện trong tuần

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|---|---|---|---|---|
| Thứ Hai | Tổ chức cuộc họp nhóm để rà soát và thống nhất các yêu cầu cho đề xuất dự án "IoT Weather Platform for Lab Research". Phân tích những hạn chế của hệ thống theo dõi thời tiết hiện tại, bao gồm việc thu thập dữ liệu thủ công, dữ liệu lưu trữ phân tán và khả năng giám sát theo thời gian thực còn hạn chế. Xác định đối tượng sử dụng là 5 thành viên nghiên cứu của ITea Lab, đồng thời làm rõ các vấn đề cần giải quyết, mục tiêu, phạm vi và kết quả kỳ vọng của dự án. | 16/11/2026 | 16/11/2026 | [AWS IoT Core Overview](https://docs.aws.amazon.com/iot/latest/developerguide/what-is-aws-iot.html) |
| Thứ Ba | Thiết kế quy trình thu thập dữ liệu Telemetry từ cảm biến ESP32 thông qua thiết bị Raspberry Pi Edge đến AWS IoT Core bằng giao thức MQTT. Tìm hiểu AWS IoT Core Rules để định tuyến dữ liệu nhận được đến các dịch vụ Backend. Thiết kế cấu trúc Amazon S3 Data Lake nhằm phân tách dữ liệu Raw và Processed. Rà soát luồng dữ liệu và xem xét khả năng mở rộng hệ thống từ 5 lên 15 trạm thời tiết. | 17/11/2026 | 17/11/2026 | [AWS IoT Rules](https://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html) <br> [Building Data Lakes on AWS](https://aws.amazon.com/solutions/implementations/data-lake-solution/) |
| Thứ Tư | Tìm hiểu giải pháp xử lý và phân tích dữ liệu bằng AWS Glue, bao gồm Glue Crawlers và Data Catalog để khám phá, tổ chức dữ liệu. Xác định vai trò của AWS Lambda trong việc xử lý dữ liệu đầu vào và hỗ trợ các hoạt động Backend. Đánh giá Amazon API Gateway để cung cấp Backend API, AWS Amplify để triển khai giao diện Dashboard Next.js và Amazon Cognito để xác thực người dùng. Phân biệt AWS CDK dùng cho Infrastructure as Code với AWS SDK dùng để tích hợp các dịch vụ AWS ở cấp độ ứng dụng. | 18/11/2026 | 18/11/2026 | [AWS Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html) <br> [Amazon Cognito User Pools](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| Thứ Năm | Xây dựng các sơ đồ kiến trúc hệ thống. Thiết kế Edge Architecture mô tả luồng dữ liệu từ cảm biến ESP32 đến thiết bị Raspberry Pi chạy Docker Container, sau đó truyền dữ liệu Telemetry bằng MQTT thông qua Wi-Fi. Thiết kế Platform Architecture thể hiện sự tương tác giữa AWS IoT Core, S3, AWS Glue, Lambda, API Gateway, Amplify và Cognito. Xây dựng bảng đánh giá rủi ro bao gồm mất kết nối mạng, lỗi cảm biến, mất dữ liệu và vượt ngân sách. Đề xuất các phương án giảm thiểu như lưu trữ dữ liệu tạm thời tại Edge, cơ chế gửi lại dữ liệu và giám sát tài nguyên. | 19/11/2026 | 19/11/2026 | [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) |
| Thứ Sáu | Sử dụng AWS Pricing Calculator để ước tính chi phí vận hành hàng tháng. Rà soát chi phí dự kiến của AWS Lambda, Amazon S3, AWS Amplify, AWS Glue và AWS IoT Core. Tổng hợp mức chi phí sơ bộ khoảng $0.70/tháng, tương đương $8.40/năm, dựa trên các giả định về cấu hình và mức sử dụng. Kiểm tra các giả định tính toán và xác định những dịch vụ có thể phát sinh chi phí tăng theo dung lượng dữ liệu hoặc mức độ sử dụng. Hoàn thiện nội dung đề xuất, sắp xếp sơ đồ kiến trúc và bảng dự toán chi phí, tích hợp nội dung song ngữ vào cấu trúc Hugo tại `content/2-Proposal/`. Kiểm tra giao diện hiển thị và các đường dẫn tài liệu trên website. | 20/11/2026 | 20/11/2026 | [AWS Pricing Calculator](https://calculator.aws/) |

## Kết quả đạt được trong Tuần 9

- Xây dựng bản đề xuất dự án nhóm "IoT Weather Platform for Lab Research" nhằm giải quyết những hạn chế của việc theo dõi thời tiết thủ công và quản lý dữ liệu phân tán.
- Xác định phạm vi dự án với quy mô triển khai ban đầu gồm 5 trạm thời tiết sử dụng Raspberry Pi và ESP32, có khả năng mở rộng lên 15 trạm.
- Thiết kế kiến trúc AWS Serverless đề xuất, tích hợp AWS IoT Core, Amazon S3 Data Lake, AWS Glue, Lambda, API Gateway, Amplify và Cognito.
- Xây dựng luồng thu thập dữ liệu Telemetry giữa các thiết bị Edge và nền tảng AWS Cloud thông qua giao thức MQTT.
- Hoàn thành các sơ đồ kiến trúc mô tả cả Edge Architecture và Platform Architecture.
- Xây dựng bảng quản lý rủi ro liên quan đến mất kết nối mạng, lỗi cảm biến, mất dữ liệu và vượt ngân sách, kèm theo các phương án giảm thiểu.
- Hoàn thành dự toán chi phí hạ tầng sơ bộ khoảng $0.70/tháng bằng AWS Pricing Calculator, dựa trên các giả định sử dụng đã xác định.
- Sắp xếp và tích hợp tài liệu Proposal song ngữ vào nền tảng Hugo tại thư mục `content/2-Proposal/`.
