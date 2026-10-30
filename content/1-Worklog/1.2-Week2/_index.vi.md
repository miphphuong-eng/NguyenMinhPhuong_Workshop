---
title: "1.2. Nhật ký công việc Tuần 2"
weight: 2
draft: false
---

## Mục tiêu Tuần 2

- Tìm hiểu kiến trúc mạng ảo Amazon Virtual Private Cloud (Amazon VPC) và các thành phần cơ bản.
- Hiểu cách phân chia địa chỉ IPv4 CIDR Block và thiết kế hệ thống mạng trên AWS.
- Phân biệt Public Subnet và Private Subnet dựa trên cấu hình định tuyến và khả năng kết nối Internet.
- Nắm được chức năng và nguyên lý hoạt động của Route Tables, Internet Gateway và NAT Gateway.
- Tìm hiểu các cơ chế bảo mật mạng trong VPC, bao gồm Security Groups và Network ACLs.
- Thực hành tạo VPC, cấu hình Subnet và thiết lập kết nối giữa các tài nguyên AWS.
- Kiểm tra khả năng kết nối mạng giữa EC2 Instance và Internet.
- Thảo luận cùng 4 thành viên để xây dựng ý tưởng dự án AWS.
- Xác định vấn đề cần giải quyết, đối tượng người dùng mục tiêu và phạm vi triển khai ban đầu của dự án.
- Nghiên cứu và lựa chọn các dịch vụ AWS phù hợp để phục vụ quá trình phát triển dự án nhóm.

---

## Các công việc thực hiện trong tuần

| Thứ | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :---: | :--- | :---: | :---: | :--- |
| **Thứ 2** | - Thảo luận cùng 4 thành viên trong nhóm về định hướng dự án AWS.<br>- Brainstorm và đề xuất các ý tưởng dự án có khả năng triển khai trên nền tảng Cloud.<br>- Xác định vấn đề thực tế cần giải quyết và đối tượng người dùng mục tiêu (Target Users).<br>- Thảo luận phạm vi chức năng ban đầu (Project Scope) và các yêu cầu chính của dự án.<br>- Tìm hiểu tổng quan về Amazon VPC và vai trò của VPC trong kiến trúc hệ thống AWS. | 28/09/2026 | 28/09/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| **Thứ 3** | - Tìm hiểu kiến thức nền tảng về Amazon VPC và cách hoạt động của mạng riêng ảo trên AWS.<br>- Nghiên cứu IPv4 CIDR Block và cách xác định phạm vi địa chỉ IP cho VPC.<br>- Tìm hiểu cách phân chia Public Subnet và Private Subnet.<br>- Nghiên cứu chức năng của Route Table và Internet Gateway.<br>- Phân tích luồng dữ liệu giữa các Subnet và Internet.<br>- Phác thảo sơ đồ kiến trúc mạng VPC trước khi tiến hành triển khai thực tế. | 29/09/2026 | 29/09/2026 | [Amazon VPC Workshop](https://000003.awsstudygroup.com/)<br>[VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html)<br>[Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)<br>[Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| **Thứ 4** | - Thực hành tạo Amazon VPC và cấu hình IPv4 CIDR Block.<br>- Tạo Public Subnet và Private Subnet bên trong VPC.<br>- Tạo Internet Gateway và gắn vào VPC.<br>- Tạo Route Table cho Public Subnet và cấu hình tuyến mặc định `0.0.0.0/0` trỏ đến Internet Gateway.<br>- Liên kết Route Table với Public Subnet tương ứng.<br>- Khởi chạy EC2 Instance trong Public Subnet và Private Subnet để kiểm tra cấu hình mạng.<br>- Kiểm tra khả năng kết nối và phân tích sự khác biệt giữa hai loại Subnet. | 30/09/2026 | 30/09/2026 | [Amazon VPC Workshop](https://000003.awsstudygroup.com/)<br>[Create EC2 Server](https://000003.awsstudygroup.com/4-createec2server/4.1-createec2/)<br>[Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| **Thứ 5** | - Tìm hiểu cơ chế bảo mật mạng thông qua Security Groups và Network ACLs.<br>- Phân biệt Security Groups hoạt động ở cấp độ Network Interface và Network ACLs hoạt động ở cấp độ Subnet.<br>- Tìm hiểu đặc điểm Stateful của Security Groups và Stateless của Network ACLs.<br>- Thực hành cấu hình Inbound Rules và Outbound Rules cho từng lớp bảo mật.<br>- Tìm hiểu các cổng kết nối phổ biến như SSH (22) và HTTP (80).<br>- Kiểm tra lưu lượng mạng thông qua SSH, HTTP và ICMP (Ping).<br>- Quan sát kết quả khi thay đổi các quy tắc cho phép hoặc từ chối kết nối. | 01/10/2026 | 01/10/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)<br>[Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) |
| **Thứ 6** | - Tìm hiểu khái niệm và nguyên lý hoạt động của NAT Gateway.<br>- Phân biệt chức năng của NAT Gateway và Internet Gateway trong kiến trúc mạng AWS.<br>- Thực hành tạo NAT Gateway bên trong Public Subnet.<br>- Cấp phát và gắn Elastic IP cho NAT Gateway.<br>- Cập nhật Route Table của Private Subnet với tuyến mặc định `0.0.0.0/0` trỏ đến NAT Gateway.<br>- Kiểm tra khả năng truy cập Internet theo chiều outbound từ EC2 Instance trong Private Subnet.<br>- Phân tích cách NAT Gateway hỗ trợ tài nguyên Private Subnet truy cập Internet mà không cần nhận kết nối khởi tạo trực tiếp từ Internet. | 02/10/2026 | 02/10/2026 | [NAT Gateway Workshop](https://000003.awsstudygroup.com/4-createec2server/4.3-natgateway/)<br>[NAT Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| **Chủ nhật** | - Tổng hợp kiến thức về Amazon VPC và các thành phần mạng đã tìm hiểu trong tuần.<br>- Kiểm tra lại cấu hình VPC, Public Subnet, Private Subnet, Route Tables, Internet Gateway và NAT Gateway.<br>- Rà soát các quy tắc Security Groups và Network ACLs.<br>- Hoàn thiện sơ đồ kiến trúc mạng VPC đã thiết kế.<br>- Tổng hợp kết quả thực hành và chụp ảnh màn hình minh chứng cho từng bước cấu hình.<br>- Kiểm tra trạng thái các tài nguyên AWS và dọn dẹp những tài nguyên không còn sử dụng để hạn chế phát sinh chi phí.<br>- Tổng hợp nội dung và hoàn thiện Worklog Tuần 2. | 04/10/2026 | 04/10/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)<br>[AWS Cost Management](https://docs.aws.amazon.com/cost-management/) |

---

## Kết quả đạt được trong Tuần 2

- Làm việc và trao đổi cùng 4 thành viên trong nhóm để xây dựng định hướng ban đầu cho dự án AWS.
- Đề xuất và thảo luận các ý tưởng dự án, xác định vấn đề cần giải quyết, đối tượng người dùng mục tiêu và phạm vi triển khai ban đầu.
- Hiểu được kiến trúc và chức năng cơ bản của Amazon VPC trong việc xây dựng hệ thống mạng riêng ảo trên AWS.
- Nắm được cách sử dụng IPv4 CIDR Block để xác định phạm vi địa chỉ IP và phân chia các Subnet.
- Phân biệt được Public Subnet và Private Subnet dựa trên cấu hình Route Table và khả năng kết nối Internet.
- Hiểu được vai trò của Route Tables trong việc định tuyến lưu lượng mạng giữa các Subnet và Internet.
- Thực hành tạo Amazon VPC, cấu hình IPv4 CIDR Block và triển khai Public Subnet, Private Subnet.
- Tạo và gắn Internet Gateway vào VPC, đồng thời cấu hình Route Table để cho phép Public Subnet kết nối Internet.
- Thực hành khởi chạy EC2 Instance trong các Subnet khác nhau và kiểm tra khả năng kết nối mạng.
- Hiểu được sự khác biệt giữa Security Groups và Network ACLs:
  - Security Groups hoạt động ở cấp độ tài nguyên và sử dụng cơ chế Stateful.
  - Network ACLs hoạt động ở cấp độ Subnet và sử dụng cơ chế Stateless.
- Thực hành cấu hình Inbound Rules và Outbound Rules để kiểm soát lưu lượng truy cập mạng.
- Kiểm tra khả năng kết nối thông qua SSH, HTTP và ICMP (Ping), đồng thời quan sát hoạt động của các quy tắc bảo mật.
- Hiểu được nguyên lý hoạt động của NAT Gateway và vai trò của Elastic IP trong kiến trúc mạng AWS.
- Thực hành tạo NAT Gateway trong Public Subnet và cập nhật Route Table cho Private Subnet.
- Kiểm tra khả năng truy cập Internet theo chiều outbound từ EC2 Instance trong Private Subnet.
- Hoàn thiện sơ đồ kiến trúc mạng VPC, tổng hợp kết quả thực hành và lưu lại hình ảnh minh chứng.
- Nâng cao kỹ năng thiết kế mạng, cấu hình định tuyến, kiểm soát truy cập và quản lý tài nguyên trên AWS.
- Biết cách rà soát và dọn dẹp tài nguyên AWS sau khi thực hành nhằm hạn chế chi phí phát sinh không cần thiết.
