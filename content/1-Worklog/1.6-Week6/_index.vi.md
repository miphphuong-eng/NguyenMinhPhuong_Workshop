
---
title: "1.6. Nhật ký công việc Tuần 6"
weight: 6
draft: false
---

## Mục tiêu Tuần 6

- Tham gia workshop cộng đồng với hoạt động làm gấu bông để dành tặng trẻ em, góp phần vào hoạt động thiện nguyện và phát triển tinh thần làm việc nhóm, trách nhiệm với cộng đồng.
- Tìm hiểu các nguyên tắc Infrastructure as Code (IaC) và lợi ích của AWS CloudFormation trong việc tự động hóa quá trình khởi tạo, cấu hình và quản lý hạ tầng.
- Nắm được cấu trúc và cú pháp CloudFormation Template bằng YAML, bao gồm Parameters, Resources, Outputs và các thành phần quan trọng khác.
- Thực hành tự động hóa quản lý tài nguyên AWS thông qua AWS CLI, kết hợp bộ lọc JMESPath `--query` để truy xuất và định dạng thông tin tài nguyên.
- Tìm hiểu vòng đời quản lý CloudFormation Stack, bao gồm tạo Stack, cập nhật cấu hình, cơ chế Rollback và Drift Detection.
- Vận dụng kiến thức đã học để thiết kế và triển khai mô hình hạ tầng AWS hai tầng (Two-tier Architecture), bao gồm các thành phần mạng, EC2 và RDS thông qua một CloudFormation Template.

## Các công việc thực hiện trong tuần

| **Ngày** | **Công việc thực hiện** | **Ngày bắt đầu** | **Ngày hoàn thành** | **Tài liệu tham khảo** |
| :--- | :--- | :--- | :--- | :--- |
| Thứ Hai | - Tham gia workshop cộng đồng với hoạt động làm gấu bông handmade để dành tặng trẻ em.<br>- Tham gia chuẩn bị nguyên vật liệu, thực hiện các công đoạn lắp ráp và hoàn thiện những món quà gấu bông cho hoạt động thiện nguyện.<br>- Phối hợp với các thành viên tham gia, phân chia công việc và hỗ trợ nhau trong quá trình thực hiện sản phẩm.<br>- Tìm hiểu ý nghĩa của hoạt động thiện nguyện, tinh thần sẻ chia, trách nhiệm với cộng đồng và kỹ năng làm việc nhóm trong môi trường thực tập. | 26/10/2026 | 26/10/2026 | Hoạt động Workshop cộng đồng |
| Thứ Ba | - Tìm hiểu các kiến thức nền tảng về Infrastructure as Code (IaC), hiểu cách khởi tạo và quản lý hạ tầng thông qua mã nguồn thay vì cấu hình thủ công.<br>- Khám phá AWS CloudFormation và so sánh phương pháp quản lý tài nguyên trực tiếp trên AWS Console với phương pháp triển khai tự động bằng Template.<br>- Nghiên cứu cấu trúc CloudFormation Template sử dụng YAML, bao gồm các thành phần `AWSTemplateFormatVersion`, `Description`, `Parameters`, `Resources` và `Outputs`.<br>- Tìm hiểu lợi ích của việc sử dụng Template có khả năng tái sử dụng, đảm bảo tính nhất quán khi triển khai và hạn chế lỗi cấu hình giữa các môi trường. | 27/10/2026 | 27/10/2026 | [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)<br>[Template Anatomy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html) |
| Thứ Tư | - Thực hành xây dựng CloudFormation Template bằng YAML để khởi tạo các thành phần mạng cơ bản trong Amazon VPC.<br>- Khai báo các tài nguyên như `AWS::EC2::VPC`, `AWS::EC2::Subnet`, `AWS::EC2::InternetGateway`, `AWS::EC2::RouteTable` và `AWS::EC2::SubnetRouteTableAssociation`.<br>- Áp dụng các Intrinsic Functions của CloudFormation như `!Ref`, `!Sub` và `!GetAtt` để tham chiếu tài nguyên, lấy thuộc tính và thiết lập các mối quan hệ phụ thuộc giữa các thành phần.<br>- Thực hành sử dụng AWS CLI trong môi trường Linux Bash để kiểm tra trạng thái tài nguyên và truy xuất thông tin như VPC ID, địa chỉ IP Public của EC2.<br>- Sử dụng JMESPath kết hợp tùy chọn `--query` để lọc dữ liệu đầu ra và định dạng kết quả JSON, hỗ trợ quá trình quản lý tài nguyên và tự động hóa. | 28/10/2026 | 28/10/2026 | [CloudFormation Resource Reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)<br>[Intrinsic Functions](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html)<br>[AWS CLI Command Reference](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/index.html)<br>[Filtering AWS CLI Output](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-filter.html) |
| Thứ Năm | - Mở rộng CloudFormation Template bằng cách bổ sung Security Groups, EC2 Instances và RDS Database để xây dựng mô hình hạ tầng hai tầng cơ bản.<br>- Kiểm tra các mối quan hệ phụ thuộc giữa tài nguyên và thiết lập quyền truy cập mạng phù hợp giữa tầng ứng dụng và tầng cơ sở dữ liệu.<br>- Tìm hiểu CloudFormation Stack Events và cơ chế tự động Rollback khi quá trình khởi tạo tài nguyên hoặc cập nhật Stack xảy ra lỗi.<br>- Nghiên cứu quy trình Stack Updates và Drift Detection nhằm phát hiện sự khác biệt giữa cấu hình thực tế của tài nguyên AWS và cấu hình được khai báo trong Template.<br>- Thực hành triển khai hạ tầng bằng lệnh `aws cloudformation create-stack` và theo dõi tiến trình thông qua `aws cloudformation describe-stack-events`.<br>- Kiểm tra trạng thái Stack, xem kết quả trong phần Outputs và truy xuất Application Endpoint nếu đã được cấu hình.<br>- Lưu trữ file `template.yaml`, chụp ảnh màn hình và tổng hợp kết quả triển khai làm minh chứng cho quá trình thực hành tự động hóa hạ tầng. | 29/10/2026 | 29/10/2026 | [Stack Management](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacks.html)<br>[Detecting Drift](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-stack-drift.html)<br>[AWS CLI CloudFormation](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/cloudformation/index.html)<br>[Deploying Stacks](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stacks.html) |

## Kết quả đạt được trong Tuần 6

- Tham gia workshop cộng đồng và đóng góp vào hoạt động làm gấu bông handmade để dành tặng trẻ em, qua đó nâng cao tinh thần làm việc nhóm và ý thức trách nhiệm với cộng đồng.
- Hiểu được các nguyên tắc cơ bản của Infrastructure as Code (IaC) và lợi ích của việc tự động hóa triển khai hạ tầng, bao gồm tính nhất quán, khả năng tái sử dụng và giảm thiểu lỗi cấu hình thủ công.
- Nắm được cấu trúc CloudFormation Template bằng YAML, cách khai báo Parameters, Resources, Outputs và sử dụng các Intrinsic Functions như `!Ref`, `!Sub` và `!GetAtt`.
- Thực hành khai báo các tài nguyên mạng AWS như VPC, Subnets, Internet Gateway và Route Tables thông qua CloudFormation Template.
- Nâng cao kỹ năng sử dụng AWS CLI, kết hợp JMESPath `--query` để lọc, truy xuất thông tin tài nguyên và định dạng dữ liệu phục vụ các tác vụ tự động hóa.
- Hiểu rõ hơn về vòng đời quản lý CloudFormation Stack, mối quan hệ phụ thuộc giữa các tài nguyên, quy trình cập nhật Stack, cơ chế Rollback và Drift Detection.
- Thực hành triển khai mô hình hạ tầng hai tầng bao gồm các thành phần mạng, EC2 và RDS thông qua CloudFormation kết hợp AWS CLI.
- Hoàn thiện và lưu trữ file `template.yaml`, đồng thời tổng hợp ảnh chụp màn hình và kết quả triển khai để làm tài liệu minh chứng cho quá trình thực hành tự động hóa hạ tầng.
