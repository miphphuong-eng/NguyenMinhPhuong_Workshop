
---
title: "1.3. Nhật ký công việc Tuần 3"
weight: 3
draft: false
---

## Mục tiêu Tuần 3

- Tìm hiểu chuyên sâu về Amazon S3 Object Storage, cấu trúc Bucket, Object Key, Metadata và cơ chế Versioning.
- Phân biệt các lớp lưu trữ S3 (Standard, Intelligent-Tiering, Standard-IA, Glacier) nhằm tối ưu chi phí lưu trữ dữ liệu.
- Nắm vững các phương pháp bảo mật S3, bao gồm Block Public Access, Bucket Policies, ACLs và Server-Side Encryption (SSE-S3, SSE-KMS).
- Tìm hiểu các thành phần cốt lõi của AWS Identity and Access Management (IAM), bao gồm Users, Groups, Roles và Policies.
- Hiểu và áp dụng nguyên tắc Principle of Least Privilege trong quản lý quyền truy cập trên AWS.
- Tích hợp thư viện AWSSDK.S3 vào ứng dụng Backend sử dụng C#/.NET.
- Xây dựng các chức năng tải lên, tải xuống và xóa Object trên Amazon S3.
- Triển khai Pre-signed URLs để chia sẻ tệp an toàn trong khoảng thời gian giới hạn.
- Tìm hiểu và cấu hình CORS cho phép Frontend giao tiếp với Amazon S3.
- Thiết lập S3 Lifecycle Policies để tự động quản lý vòng đời và dọn dẹp dữ liệu không còn sử dụng.

---

## Các công việc thực hiện trong tuần

| Thứ | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :---: | :--- | :---: | :---: | :--- |
| **Thứ 2** | - Tìm hiểu tổng quan về Amazon S3 và thực hành các kiến thức cơ bản về Object Storage.<br>- Thực hành tạo S3 Bucket và tải Object lên Bucket.<br>- Tìm hiểu cấu trúc Object Key và cách quản lý Metadata của các Object.<br>- Thực hành bật và kiểm tra cơ chế Object Versioning để quản lý nhiều phiên bản của dữ liệu.<br>- Phân tích các lớp lưu trữ S3 gồm Standard, Intelligent-Tiering, Standard-IA và Glacier.<br>- So sánh đặc điểm, mục đích sử dụng và chi phí của từng lớp lưu trữ. | 05/10/2026 | 05/10/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)<br>[S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/) |
| **Thứ 3** | - Tìm hiểu các cơ chế bảo mật dữ liệu trên Amazon S3.<br>- Thực hành bật Block Public Access nhằm ngăn chặn việc vô tình công khai dữ liệu ra Internet.<br>- Nghiên cứu cách hoạt động của Bucket Policies và Access Control Lists (ACLs).<br>- Viết các chính sách Bucket Policy bằng JSON để kiểm soát quyền truy cập vào tài nguyên S3.<br>- Tìm hiểu cơ chế mã hóa dữ liệu khi lưu trữ (Encryption at Rest).<br>- Thực hành cấu hình Server-Side Encryption với SSE-S3 và SSE-KMS.<br>- Kiểm tra quyền truy cập và trạng thái mã hóa của các Object trong Bucket. | 06/10/2026 | 06/10/2026 | [Amazon S3 Security](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html)<br>[S3 Bucket Policies](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-policies.html) |
| **Thứ 4** | - Tìm hiểu các kiến thức nền tảng về AWS Identity and Access Management (IAM).<br>- Phân biệt các thành phần IAM gồm Users, Groups, Roles và Policies.<br>- Tìm hiểu nguyên tắc Principle of Least Privilege trong quản lý bảo mật Cloud.<br>- Thực hành tạo IAM User dành riêng cho ứng dụng Backend.<br>- Xây dựng IAM Policy bằng JSON với các quyền được giới hạn cụ thể như `s3:GetObject` và `s3:PutObject`.<br>- Kiểm tra quyền truy cập của IAM User và đảm bảo ứng dụng chỉ có thể thực hiện những thao tác được cấp phép.<br>- Tìm hiểu cách quản lý thông tin xác thực AWS an toàn. | 07/10/2026 | 07/10/2026 | [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)<br>[IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) |
| **Thứ 5** | - Tìm hiểu cách tích hợp thư viện AWSSDK.S3 vào dự án Backend sử dụng C#/.NET.<br>- Cài đặt và cấu hình package AWSSDK.S3 trong dự án.<br>- Xây dựng lớp S3Service để quản lý các thao tác với Amazon S3.<br>- Triển khai các phương thức `PutObjectAsync`, `GetObjectAsync` và `DeleteObjectAsync` để hỗ trợ tải lên, tải xuống và xóa Object.<br>- Tìm hiểu và triển khai Pre-signed URLs để chia sẻ Object riêng tư mà không cần công khai Bucket.<br>- Cấu hình thời hạn hiệu lực của Pre-signed URLs trong khoảng 15–30 phút.<br>- Tìm hiểu cách quản lý AWS Access Key và Secret Key thông qua Environment Variables để hạn chế lộ thông tin xác thực. | 08/10/2026 | 08/10/2026 | [AWS SDK for .NET S3 Guide](https://docs.aws.amazon.com/sdk-for-net/v3/developer-guide/s3-index.html)<br>[Pre-signed URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/ShareObjectPreSignedURL.html) |
| **Thứ 6** | - Thực hành kiểm thử và xử lý các vấn đề phát sinh trong quá trình tích hợp Amazon S3 với ứng dụng Backend và Frontend.<br>- Phân tích và khắc phục lỗi CORS khi trình duyệt Frontend sử dụng Pre-signed URLs để tải tệp lên S3.<br>- Cấu hình CORS Rules cho S3 Bucket với các thuộc tính AllowedOrigins và AllowedMethods phù hợp.<br>- Kiểm tra hoạt động tải tệp từ trình duyệt sau khi cấu hình CORS.<br>- Thiết lập S3 Lifecycle Rules để tự động xóa các tệp tạm thời không còn sử dụng trong thư mục `temp/` sau 7 ngày.<br>- Kiểm tra lại các chính sách bảo mật, quyền IAM và chức năng xử lý Object.<br>- Chụp ảnh màn hình minh chứng, tổng hợp kết quả thực hành và hoàn thiện Worklog Tuần 3. | 09/10/2026 | 09/10/2026 | [S3 CORS Configuration](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html)<br>[S3 Lifecycle Management](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html) |

---

## Kết quả đạt được trong Tuần 3

- Hiểu chuyên sâu về Amazon S3 Object Storage, cấu trúc Bucket, Object, Metadata và cơ chế Versioning.
- Phân biệt được các lớp lưu trữ S3 và hiểu cách lựa chọn lớp lưu trữ phù hợp nhằm tối ưu hiệu năng và chi phí.
- Thực hành tạo S3 Bucket, tải Object lên, quản lý Metadata và kiểm tra các phiên bản dữ liệu.
- Nắm được các cơ chế bảo mật trên Amazon S3, bao gồm Block Public Access, Bucket Policies và ACLs.
- Thực hành xây dựng Bucket Policies bằng JSON để kiểm soát quyền truy cập vào tài nguyên S3.
- Hiểu và cấu hình mã hóa dữ liệu khi lưu trữ bằng Server-Side Encryption, bao gồm SSE-S3 và SSE-KMS.
- Nắm được các thành phần cốt lõi của AWS IAM gồm Users, Groups, Roles và Policies.
- Hiểu và áp dụng nguyên tắc Principle of Least Privilege nhằm giới hạn quyền truy cập theo đúng nhu cầu của ứng dụng.
- Thực hành tạo IAM User và cấu hình JSON Policy với các quyền truy cập S3 được giới hạn cụ thể.
- Tích hợp thành công thư viện AWSSDK.S3 vào dự án Backend sử dụng C#/.NET.
- Xây dựng lớp S3Service hỗ trợ các chức năng tải lên, tải xuống và xóa Object thông qua các phương thức bất đồng bộ.
- Triển khai Pre-signed URLs để chia sẻ các Object riêng tư một cách an toàn mà không cần công khai S3 Bucket.
- Hiểu cách quản lý AWS Access Key và Secret Key thông qua Environment Variables.
- Tìm hiểu và cấu hình CORS để cho phép ứng dụng Frontend giao tiếp với Amazon S3.
- Thực hành xử lý các lỗi liên quan đến CORS khi sử dụng Pre-signed URLs để tải tệp lên S3.
- Thiết lập S3 Lifecycle Rules để tự động quản lý và dọn dẹp các tệp tạm thời sau thời gian quy định.
- Nâng cao kỹ năng tích hợp dịch vụ lưu trữ Cloud với ứng dụng Backend C#/.NET, đồng thời cải thiện kiến thức về bảo mật và quản lý dữ liệu trên AWS.
