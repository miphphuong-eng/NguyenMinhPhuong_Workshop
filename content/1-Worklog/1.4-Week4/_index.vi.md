
---
title: "1.4. Nhật ký công việc Tuần 4"
weight: 4
draft: false
---

## Mục tiêu Tuần 4

- Tìm hiểu chuyên sâu về kiến trúc và khả năng vận hành của dịch vụ cơ sở dữ liệu quan hệ được quản lý trên AWS thông qua Amazon Relational Database Service (Amazon RDS).
- Nghiên cứu và so sánh các Database Engine được hỗ trợ như PostgreSQL, MySQL, MariaDB và Amazon Aurora để lựa chọn hệ quản trị cơ sở dữ liệu phù hợp với yêu cầu của ứng dụng.
- Hiểu nguyên lý hoạt động của Multi-AZ Deployment nhằm tăng tính sẵn sàng (High Availability) và Read Replicas nhằm mở rộng khả năng xử lý các truy vấn đọc.
- Thực hành tạo DB Subnet Group, cấu hình Security Groups và triển khai Amazon RDS an toàn trong Private Subnets.
- Tìm hiểu quy trình kết nối ứng dụng Backend với Amazon RDS và thực hành quản lý cấu trúc cơ sở dữ liệu thông qua SQL Migration Scripts.
- Nắm được cơ chế Automated Backups, Manual DB Snapshots và quy trình khôi phục cơ sở dữ liệu khi xảy ra sự cố.
- Áp dụng các nguyên tắc bảo mật mạng nhằm giới hạn quyền truy cập vào cơ sở dữ liệu từ những tài nguyên được cấp phép.

---

## Các công việc thực hiện trong tuần

| Thứ | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :---: | :--- | :---: | :---: | :--- |
| **Thứ 2** | - Tìm hiểu tổng quan về Amazon RDS và vai trò của dịch vụ trong việc triển khai, quản lý cơ sở dữ liệu quan hệ trên AWS.<br>- So sánh mô hình tự quản lý Database trên EC2 với mô hình sử dụng Amazon RDS được AWS quản lý.<br>- Nghiên cứu các Database Engine phổ biến như PostgreSQL, MySQL, MariaDB và Amazon Aurora.<br>- Tìm hiểu các thành phần cấu hình của DB Instance như Instance Classes, Storage Types (gp2, gp3, io1), DB Parameter Groups và Option Groups.<br>- Phân tích cách lựa chọn cấu hình tài nguyên cơ sở dữ liệu dựa trên hiệu năng, dung lượng lưu trữ và nhu cầu sử dụng của ứng dụng. | 12/10/2026 | 12/10/2026 | [Amazon RDS User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)<br>[RDS Storage Types](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html) |
| **Thứ 3** | - Tìm hiểu cơ chế High Availability (HA) trong Amazon RDS thông qua Multi-AZ Deployment.<br>- Nghiên cứu cơ chế sao chép dữ liệu đồng bộ đến Standby Instance và khả năng tự động chuyển đổi dự phòng (Automatic Failover).<br>- Thực hành tìm hiểu cấu hình Multi-AZ để tăng khả năng duy trì hoạt động của cơ sở dữ liệu khi xảy ra sự cố.<br>- Tìm hiểu Read Replicas và cơ chế sao chép dữ liệu bất đồng bộ (Asynchronous Replication).<br>- Phân tích cách sử dụng Read Replicas để phân tán các truy vấn đọc và giảm tải cho Database Instance chính.<br>- So sánh mục đích sử dụng của Multi-AZ và Read Replicas trong kiến trúc hệ thống thực tế. | 13/10/2026 | 13/10/2026 | [RDS High Availability (Multi-AZ)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)<br>[RDS Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html) |
| **Thứ 4** | - Thực hành tạo DB Subnet Group và lựa chọn các Private Subnets thuộc nhiều Availability Zones khác nhau.<br>- Tìm hiểu vai trò của DB Subnet Group trong việc xác định vị trí triển khai Amazon RDS trong VPC.<br>- Tạo và cấu hình Security Group dành riêng cho RDS Instance.<br>- Thiết lập Inbound Rules chỉ cho phép EC2 Web Server Security Group truy cập Database thông qua các cổng phù hợp như PostgreSQL (5432) hoặc MySQL (3306).<br>- Thực hành triển khai Amazon RDS PostgreSQL Instance trong Private Subnet.<br>- Tắt tùy chọn Public Accessibility để ngăn cơ sở dữ liệu được truy cập trực tiếp từ Internet.<br>- Kiểm tra lại cấu hình mạng và các quy tắc bảo mật sau khi triển khai. | 14/10/2026 | 14/10/2026 | [RDS Subnet Groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceinaVPC.html)<br>[RDS Security Groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html) |
| **Thứ 5** | - Tìm hiểu quy trình kết nối từ ứng dụng Backend hoặc EC2 Instance đến Amazon RDS PostgreSQL.<br>- Thực hành kết nối đến RDS Instance từ EC2 Instance trong Public Subnet bằng công cụ `psql` hoặc pgAdmin.<br>- Kiểm tra kết nối thông qua Endpoint, Port, Database Name và thông tin xác thực của cơ sở dữ liệu.<br>- Thực hành viết và chạy SQL Migration Scripts để tạo Tables, Indexes và khởi tạo dữ liệu ban đầu cho ứng dụng.<br>- Kiểm tra cấu trúc dữ liệu sau khi thực hiện Migration.<br>- Tìm hiểu cách cấu hình Database Connection String thông qua Environment Variables trên Backend Server.<br>- Áp dụng các biện pháp bảo vệ thông tin đăng nhập, tránh lưu trực tiếp thông tin kết nối trong Source Code. | 15/10/2026 | 15/10/2026 | [Connect to RDS Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html)<br>[PostgreSQL on RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_PostgreSQL.html) |
| **Thứ 6** | - Tìm hiểu cơ chế Automated Backups và các khái niệm Recovery Point Objective (RPO), Recovery Time Objective (RTO).<br>- Phân biệt Automated Backups và Manual DB Snapshots trong việc bảo vệ và khôi phục dữ liệu.<br>- Thực hành tạo Manual DB Snapshot từ RDS Instance hiện có.<br>- Thử nghiệm khôi phục một DB Instance mới từ Snapshot đã tạo để kiểm tra khả năng phục hồi dữ liệu.<br>- Kiểm tra lại các Security Group Rules nhằm đảm bảo các cổng Database không bị mở công khai ra Internet.<br>- Rà soát cấu hình Multi-AZ, DB Subnet Group, Public Accessibility và quyền truy cập cơ sở dữ liệu.<br>- Chụp ảnh màn hình minh chứng, tổng hợp kết quả thực hành và hoàn thiện Worklog Tuần 4. | 16/10/2026 | 16/10/2026 | [RDS Backups & Snapshots](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html)<br>[Restoring DB Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_RestoreFromSnapshot.html) |

---

## Kết quả đạt được trong Tuần 4

- Hiểu được kiến trúc, chức năng và những lợi ích vận hành của Amazon RDS so với việc tự triển khai và quản lý Database trên EC2 Instance.
- Nắm được đặc điểm của các Database Engine được hỗ trợ như PostgreSQL, MySQL, MariaDB và Amazon Aurora.
- Hiểu cách lựa chọn DB Instance Classes và Storage Types phù hợp với yêu cầu về hiệu năng, dung lượng và chi phí.
- Nắm được nguyên lý hoạt động của Multi-AZ Deployment trong việc tăng tính sẵn sàng và hỗ trợ tự động chuyển đổi dự phòng khi xảy ra sự cố.
- Hiểu được cơ chế hoạt động của Read Replicas và khả năng mở rộng hệ thống thông qua việc phân tán các truy vấn đọc.
- Phân biệt được mục đích sử dụng của Multi-AZ Deployment và Read Replicas trong kiến trúc cơ sở dữ liệu.
- Thực hành tạo DB Subnet Group bao gồm các Private Subnets thuộc nhiều Availability Zones.
- Triển khai Amazon RDS PostgreSQL Instance trong Private Subnets và tắt Public Accessibility nhằm hạn chế truy cập trực tiếp từ Internet.
- Cấu hình Security Groups để chỉ cho phép các EC2 Web Server được cấp quyền kết nối đến RDS Instance thông qua các Database Ports cần thiết.
- Thiết lập thành công kết nối giữa EC2 Instance và Amazon RDS PostgreSQL thông qua Endpoint và thông tin xác thực phù hợp.
- Thực hành xây dựng và thực thi SQL Migration Scripts để tạo Tables, Indexes và khởi tạo dữ liệu ban đầu cho ứng dụng.
- Biết cách cấu hình Database Connection String thông qua Environment Variables nhằm bảo vệ thông tin kết nối của Backend Application.
- Hiểu được vai trò của Automated Backups trong việc bảo vệ dữ liệu và hỗ trợ khôi phục cơ sở dữ liệu.
- Phân biệt được Automated Backups và Manual DB Snapshots, đồng thời hiểu quy trình khôi phục DB Instance từ Snapshot.
- Thực hành tạo Manual DB Snapshot và kiểm tra khả năng khôi phục dữ liệu bằng cách triển khai một DB Instance mới.
- Nâng cao kỹ năng thiết kế, triển khai và bảo mật hệ thống cơ sở dữ liệu trên AWS.
- Hoàn thiện tài liệu thực hành và lưu lại hình ảnh minh chứng về kiến trúc RDS, cấu hình mạng và các cơ chế bảo vệ dữ liệu.
