---
title: "Blog 1"
date: 2026-11-23
weight: 1
chapter: false
pre: "<b> 3.1. </b>"
---

# XÂY DỰNG CI/CD PIPELINE TRÊN AWS: TÍCH HỢP DEVSECOPS ĐỂ KIỂM TRA BẢO MẬT TRƯỚC KHI TRIỂN KHAI PRODUCTION

Trong quá trình phát triển phần mềm hiện đại, việc triển khai mã nguồn lên môi trường Production một cách nhanh chóng là chưa đủ. Một ứng dụng có thể hoạt động bình thường nhưng vẫn tồn tại các lỗ hổng bảo mật, thư viện bên thứ ba có nguy cơ mất an toàn hoặc cấu hình AWS chưa được bảo vệ đúng cách.

Nếu các bước kiểm tra bảo mật chỉ được thực hiện sau khi ứng dụng đã triển khai, việc phát hiện và khắc phục vấn đề có thể mất nhiều thời gian hơn, làm tăng chi phí và thậm chí ảnh hưởng đến hoạt động của hệ thống.

Một giải pháp hiệu quả là tích hợp **DevSecOps** vào CI/CD Pipeline trên AWS. Phương pháp này đưa các bước kiểm tra bảo mật vào xuyên suốt quá trình phát triển và triển khai, giúp đội ngũ phát hiện những rủi ro tiềm ẩn trước khi ứng dụng được đưa lên môi trường Production.

### Tổng quan kiến trúc (Architecture Overview)

Kiến trúc CI/CD tích hợp DevSecOps sử dụng nhiều dịch vụ AWS để tự động hóa quá trình build ứng dụng, kiểm thử bảo mật, triển khai và giám sát hệ thống.

Các thành phần chính bao gồm:

- **Git:** Quản lý mã nguồn và ghi nhận những thay đổi do lập trình viên thực hiện.
- **AWS CodePipeline:** Điều phối toàn bộ quy trình CI/CD.
- **AWS CodeCommit:** Lưu trữ repository chứa mã nguồn của ứng dụng.
- **AWS CodeBuild:** Build ứng dụng và thực hiện các bước kiểm tra bảo mật.
- **AWS CodeDeploy:** Triển khai ứng dụng lên môi trường mục tiêu.
- **Amazon S3 & AWS CodeArtifact:** Lưu trữ các build artifact và dependency cần thiết trong quá trình build và triển khai.
- **AWS Lambda:** Phân tích kết quả quét bảo mật và hỗ trợ xử lý các phát hiện bảo mật.
- **AWS Security Hub:** Tập trung các phát hiện bảo mật từ nhiều nguồn khác nhau.
- **AWS Config:** Theo dõi và đánh giá cấu hình các tài nguyên AWS.
- **Amazon ECS:** Vận hành ứng dụng trong môi trường Staging và Production.

### Quy trình CI/CD tích hợp DevSecOps

Quy trình được chia thành nhiều giai đoạn nhằm đảm bảo ứng dụng được kiểm tra đầy đủ trước khi phát hành lên môi trường Production.

**1. Commit – Đẩy mã nguồn lên Git**

Khi lập trình viên hoàn thành một thay đổi trong mã nguồn, các thay đổi sẽ được commit và đẩy lên repository.

- Git ghi nhận những thay đổi được thực hiện trong mã nguồn.
- AWS CodePipeline nhận sự kiện từ repository để kích hoạt pipeline.
- Các giai đoạn build và kiểm thử được tự động thực hiện.

**2. Build & Security Scan – Kiểm tra mã nguồn**

AWS CodeBuild tiến hành build ứng dụng và tích hợp các công cụ kiểm thử bảo mật vào quy trình.

Hai phương pháp kiểm tra bảo mật quan trọng bao gồm:

- **SCA (Software Composition Analysis):**
  - Kiểm tra các thư viện bên thứ ba và những dependency mà ứng dụng đang sử dụng.
  - Phát hiện các phiên bản dependency đã được ghi nhận có lỗ hổng bảo mật hoặc tiềm ẩn rủi ro.
- **SAST (Static Application Security Testing):**
  - Phân tích mã nguồn mà không cần thực thi ứng dụng.
  - Phát hiện những đoạn mã hoặc cách viết code có thể tạo ra điểm yếu bảo mật.

Trong kiến trúc minh họa, các công cụ được sử dụng bao gồm Black Duck và SonarQube.

**3. Deploy – Triển khai lên môi trường Staging**

Sau khi hoàn thành bước build ban đầu và các kiểm tra bảo mật, ứng dụng được triển khai lên môi trường Staging.

- AWS CodeDeploy quản lý quá trình triển khai.
- Amazon ECS cung cấp môi trường để ứng dụng hoạt động.
- Staging đóng vai trò là môi trường kiểm thử trước khi ứng dụng được phát hành lên Production.

**4. Test – Kiểm thử bảo mật trong quá trình chạy ứng dụng**

Sau khi triển khai lên Staging, hệ thống tiếp tục thực hiện các bước kiểm tra bảo mật trong khi ứng dụng đang hoạt động.

- **DAST (Dynamic Application Security Testing):**
  - Kiểm tra ứng dụng đang chạy bằng cách gửi các request và phân tích response nhận được.
  - Phát hiện những lỗ hổng có thể xuất hiện trong quá trình ứng dụng thực thi.
- **IAST (Interactive Application Security Testing):**
  - Phân tích hành vi của ứng dụng trong quá trình thực thi.
  - Hỗ trợ phát hiện các vấn đề bảo mật dựa trên thông tin được thu thập khi ứng dụng đang hoạt động.

Trong kiến trúc minh họa, các công cụ được sử dụng bao gồm Appknox và Veracode.

**5. Manual Approval & Production Deployment – Phê duyệt thủ công và triển khai Production**

Trước khi ứng dụng được phát hành chính thức, kết quả kiểm thử cần được tổng hợp và đánh giá.

- Kiểm tra các vấn đề bảo mật và cảnh báo đã được phát hiện.
- Đánh giá mức độ rủi ro và xác định những vấn đề cần khắc phục.
- Yêu cầu Manual Approval trước khi tiếp tục triển khai lên Production.
- Nếu ứng dụng đáp ứng các điều kiện cần thiết, AWS CodeDeploy sẽ triển khai ứng dụng lên Amazon ECS trong môi trường Production.

Việc bổ sung bước phê duyệt thủ công giúp đội ngũ phát triển và bảo mật kiểm soát tốt hơn quá trình phát hành ứng dụng.

### Giám sát và kiểm soát bảo mật (Security Monitoring and Control)

Bên cạnh việc kiểm tra mã nguồn và ứng dụng, hệ thống cần có các cơ chế giám sát để theo dõi hoạt động và phát hiện những thay đổi bất thường.

Một số dịch vụ AWS hỗ trợ quá trình này bao gồm:

- **AWS CloudTrail:** Ghi lại các hoạt động API và những thay đổi được thực hiện trong tài khoản AWS.
- **AWS Config:** Theo dõi cấu hình tài nguyên và xác định những thay đổi không đáp ứng các yêu cầu đã đặt ra.
- **AWS Security Hub:** Tổng hợp các phát hiện bảo mật từ nhiều dịch vụ để hỗ trợ đánh giá rủi ro.
- **AWS Lambda:** Phân tích kết quả quét và hỗ trợ tự động hóa việc xử lý một số phát hiện bảo mật.
- **Amazon CloudWatch Logs & Events:** Theo dõi log, sự kiện và trạng thái thực thi của pipeline.

Việc kết hợp các dịch vụ này giúp đội ngũ DevOps và Security có cái nhìn tổng quan hơn về tình trạng bảo mật của hệ thống.

### Quản lý cấu hình và quyền truy cập (Configuration and Access Management)

Một CI/CD Pipeline an toàn không chỉ cần kiểm tra mã nguồn mà còn phải kiểm soát quyền truy cập và bảo vệ thông tin cấu hình của ứng dụng.

Các thành phần quan trọng bao gồm:

- **AWS IAM Role:**
  - Cấp quyền cần thiết cho các dịch vụ AWS để thực hiện nhiệm vụ của mình.
  - Áp dụng nguyên tắc Least Privilege bằng cách chỉ cấp những quyền thực sự cần thiết.
- **AWS Systems Manager Parameter Store:**
  - Lưu trữ và quản lý các tham số cấu hình của ứng dụng.
  - Hạn chế việc đưa trực tiếp thông tin cấu hình vào mã nguồn.
- **Amazon S3:**
  - Lưu trữ các artifact cần thiết cho quá trình build và triển khai.
- **Amazon SNS (Simple Notification Service):**
  - Gửi thông báo qua Email khi các hoạt động của pipeline hoặc quá trình kiểm tra bảo mật phát sinh sự kiện cần được chú ý.

### Các tình huống cần kiểm thử (Scenarios to Validate)

Để đảm bảo pipeline hoạt động đúng như mong đợi, cần kiểm thử một số tình huống thực tế:

- **Dependency có lỗ hổng bảo mật:** SCA phát hiện một thư viện không an toàn và đưa ra cảnh báo trước khi triển khai.
- **Vấn đề bảo mật trong mã nguồn:** SAST phát hiện những vấn đề tiềm ẩn trong giai đoạn build.
- **Lỗ hổng khi ứng dụng đang chạy:** DAST và IAST hỗ trợ phát hiện các vấn đề trong môi trường Staging.
- **Cấu hình AWS không an toàn:** AWS Config ghi nhận những tài nguyên không đáp ứng yêu cầu cấu hình.
- **Triển khai thất bại:** CloudWatch Logs hỗ trợ theo dõi và xác định nguyên nhân gây ra lỗi triển khai.
- **Phát hiện rủi ro bảo mật:** Security Hub tập trung các phát hiện để đội ngũ DevOps và Security xem xét và xử lý.

Những tình huống này giúp đánh giá khả năng phát hiện, báo cáo và kiểm soát các rủi ro bảo mật của pipeline trong suốt quy trình hoạt động.

### Những điều tôi học được (What I Learned)

Thông qua kiến trúc CI/CD tích hợp DevSecOps này, tôi hiểu rõ hơn rằng bảo mật cần được xem là một phần thiết yếu trong quá trình phát triển phần mềm, thay vì chỉ là bước kiểm tra cuối cùng trước khi phát hành.

Một số bài học quan trọng bao gồm:

- Tích hợp SCA và SAST vào giai đoạn build để phát hiện sớm các vấn đề liên quan đến dependency và mã nguồn.
- Sử dụng DAST và IAST để kiểm tra ứng dụng trong môi trường đang thực thi.
- Triển khai ứng dụng lên Staging trước khi phát hành chính thức lên Production.
- Bổ sung Manual Approval để kiểm soát những thay đổi quan trọng trước khi phát hành.
- Kết hợp Security Hub, AWS Config và CloudTrail để cải thiện khả năng giám sát và kiểm soát bảo mật.
- Áp dụng nguyên tắc IAM Least Privilege để hạn chế những quyền truy cập không cần thiết.

Điều quan trọng nhất tôi rút ra được là DevSecOps chuyển cách tiếp cận bảo mật từ việc kiểm tra sau khi triển khai sang việc kiểm tra liên tục trong suốt vòng đời phát triển phần mềm.

Nhờ đó, tổ chức có thể phát hiện lỗ hổng sớm hơn, giảm thiểu các rủi ro tiềm ẩn và cải thiện độ tin cậy của ứng dụng trước khi phát hành lên môi trường Production.

### Hình ảnh (Images)

Hình ảnh dưới đây minh họa kiến trúc AWS CI/CD Pipeline tích hợp các công cụ và dịch vụ DevSecOps nhằm thực hiện kiểm tra bảo mật, giám sát và kiểm soát trước khi triển khai ứng dụng lên môi trường Production.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/aws-devsecops-cicd-pipeline.jpg" alt="AWS CI/CD Pipeline tích hợp DevSecOps" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Hình 1 - AWS CI/CD Pipeline tích hợp DevSecOps để kiểm tra bảo mật trước khi triển khai Production</em></p>
</div>

### Tài liệu tham khảo (References)

1. AWS CodePipeline: https://docs.aws.amazon.com/codepipeline/
2. AWS CodeBuild: https://docs.aws.amazon.com/codebuild/
3. AWS CodeDeploy: https://docs.aws.amazon.com/codedeploy/
4. AWS Security Hub: https://docs.aws.amazon.com/securityhub/
5. AWS Config: https://docs.aws.amazon.com/config/
6. AWS CloudTrail: https://docs.aws.amazon.com/cloudtrail/
7. Amazon ECS: https://docs.aws.amazon.com/ecs/
