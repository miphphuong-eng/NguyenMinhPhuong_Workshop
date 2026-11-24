
# Blog 1

# XÂY DỰNG CI/CD PIPELINE TRÊN AWS: TÍCH HỢP DEVSECOPS ĐỂ KIỂM TRA BẢO MẬT TRƯỚC KHI DEPLOY PRODUCTION

Trong quá trình phát triển phần mềm, việc đưa code lên môi trường Production nhanh chóng là chưa đủ. Một ứng dụng có thể hoạt động bình thường nhưng vẫn tiềm ẩn các lỗ hổng bảo mật, thư viện bên thứ ba không an toàn hoặc cấu hình AWS chưa được bảo vệ đúng cách.

Nếu chỉ thực hiện kiểm tra bảo mật sau khi ứng dụng đã được triển khai, việc phát hiện và xử lý sự cố có thể mất nhiều thời gian, làm tăng chi phí và ảnh hưởng đến hoạt động của hệ thống.

Một giải pháp hiệu quả là tích hợp **DevSecOps** vào CI/CD Pipeline trên AWS. Cách tiếp cận này đưa các bước kiểm tra bảo mật vào xuyên suốt quy trình phát triển và triển khai, giúp phát hiện sớm rủi ro trước khi ứng dụng được đưa lên môi trường Production.

### Tổng quan kiến trúc

Kiến trúc CI/CD kết hợp DevSecOps sử dụng nhiều dịch vụ AWS để tự động hóa quá trình build, kiểm thử, triển khai và giám sát bảo mật.

Các thành phần chính bao gồm:

- **Git:** Quản lý mã nguồn và ghi nhận các thay đổi từ Developer.
- **AWS CodePipeline:** Điều phối toàn bộ quy trình CI/CD.
- **AWS CodeCommit:** Lưu trữ mã nguồn.
- **AWS CodeBuild:** Build ứng dụng và thực hiện các bước kiểm tra bảo mật.
- **AWS CodeDeploy:** Triển khai ứng dụng lên môi trường đích.
- **Amazon S3 & AWS CodeArtifact:** Lưu trữ artifact và các dependency phục vụ quá trình build, deployment.
- **AWS Lambda:** Phân tích kết quả quét bảo mật và hỗ trợ xử lý các phát hiện.
- **AWS Security Hub:** Tập trung các phát hiện bảo mật từ nhiều nguồn.
- **AWS Config:** Theo dõi và đánh giá cấu hình tài nguyên AWS.
- **Amazon ECS:** Chạy ứng dụng trong môi trường Staging và Production.

### Quy trình CI/CD kết hợp DevSecOps

Quy trình được chia thành các giai đoạn nhằm đảm bảo ứng dụng được kiểm tra trước khi triển khai chính thức.

**1. Commit – Đưa mã nguồn lên Git**

Khi Developer hoàn thành một thay đổi, mã nguồn sẽ được commit và đưa lên repository.

- Git ghi nhận các thay đổi trong mã nguồn.
- AWS CodePipeline nhận sự kiện từ repository để khởi chạy pipeline.
- Các giai đoạn build và kiểm thử được tự động thực hiện.

**2. Build & Security Scan – Kiểm tra mã nguồn**

AWS CodeBuild thực hiện quá trình build ứng dụng và tích hợp các công cụ kiểm tra bảo mật.

Hai phương pháp kiểm tra quan trọng gồm:

- **SCA (Software Composition Analysis):**
  - Kiểm tra các thư viện bên thứ ba và dependency của ứng dụng.
  - Phát hiện những phiên bản thư viện có lỗ hổng bảo mật hoặc rủi ro đã được ghi nhận.
- **SAST (Static Application Security Testing):**
  - Phân tích mã nguồn mà không cần chạy ứng dụng.
  - Phát hiện những đoạn code có khả năng gây ra vấn đề bảo mật.

Các công cụ minh họa trong kiến trúc gồm Black Duck và SonarQube.

**3. Deploy – Triển khai lên môi trường Staging**

Sau khi hoàn thành bước build và kiểm tra ban đầu, ứng dụng được triển khai lên môi trường Staging.

- AWS CodeDeploy điều phối quá trình triển khai.
- Amazon ECS cung cấp môi trường chạy ứng dụng.
- Staging được sử dụng để kiểm tra ứng dụng trước khi đưa lên Production.

**4. Test – Kiểm tra bảo mật khi ứng dụng đang chạy**

Sau khi ứng dụng được triển khai lên Staging, hệ thống tiếp tục thực hiện các bước kiểm tra bảo mật ở thời điểm runtime.

- **DAST (Dynamic Application Security Testing):**
  - Kiểm tra ứng dụng đang chạy bằng cách gửi các yêu cầu và quan sát phản hồi.
  - Phát hiện những lỗ hổng có thể xuất hiện trong quá trình ứng dụng hoạt động.
- **IAST (Interactive Application Security Testing):**
  - Phân tích hành vi của ứng dụng trong quá trình thực thi.
  - Hỗ trợ xác định các vấn đề bảo mật thông qua thông tin thu thập khi ứng dụng hoạt động.

Các công cụ minh họa gồm Appknox và Veracode.

**5. Manual Approval & Production Deployment**

Trước khi triển khai chính thức, kết quả kiểm thử cần được tổng hợp và đánh giá.

- Kiểm tra các lỗi và cảnh báo bảo mật được phát hiện.
- Đánh giá mức độ rủi ro và xác định những vấn đề cần xử lý.
- Yêu cầu Manual Approval để xác nhận trước khi triển khai Production.
- Nếu đáp ứng yêu cầu, AWS CodeDeploy triển khai ứng dụng lên Amazon ECS trong môi trường Production.

Việc bổ sung bước phê duyệt thủ công giúp đội ngũ phát triển và bảo mật kiểm soát tốt hơn quá trình phát hành.

### Giám sát và kiểm soát bảo mật

Bên cạnh việc kiểm tra mã nguồn và ứng dụng, hệ thống cần có cơ chế giám sát để theo dõi hoạt động và phát hiện những thay đổi bất thường.

Một số dịch vụ AWS hỗ trợ quá trình này:

- **AWS CloudTrail:** Ghi nhận các hoạt động API và thay đổi được thực hiện trên tài khoản AWS.
- **AWS Config:** Theo dõi cấu hình tài nguyên và phát hiện những thay đổi không tuân thủ yêu cầu.
- **AWS Security Hub:** Tổng hợp các phát hiện bảo mật từ nhiều dịch vụ để hỗ trợ đánh giá rủi ro.
- **AWS Lambda:** Phân tích kết quả quét và hỗ trợ tự động xử lý một số phát hiện bảo mật.
- **Amazon CloudWatch Logs & Events:** Theo dõi log, sự kiện và trạng thái hoạt động của pipeline.

Việc kết hợp các dịch vụ này giúp đội ngũ DevOps và Security có cái nhìn tổng quan hơn về tình trạng bảo mật của hệ thống.

### Quản lý cấu hình và quyền truy cập

Một CI/CD Pipeline an toàn không chỉ cần kiểm tra mã nguồn mà còn phải kiểm soát quyền truy cập và bảo vệ thông tin cấu hình.

Các thành phần quan trọng gồm:

- **AWS IAM Role:**
  - Cấp quyền cho từng dịch vụ AWS khi thực hiện các tác vụ.
  - Áp dụng nguyên tắc Least Privilege, chỉ cấp những quyền thực sự cần thiết.
- **AWS Systems Manager Parameter Store:**
  - Lưu trữ và quản lý các tham số cấu hình ứng dụng.
  - Hạn chế việc đưa thông tin cấu hình trực tiếp vào mã nguồn.
- **Amazon S3:**
  - Lưu trữ artifact phục vụ quá trình build và deployment.
- **Amazon SNS (Simple Notification Service):**
  - Gửi thông báo qua Email khi pipeline hoặc các bước kiểm tra phát sinh sự kiện cần xử lý.

### Các tình huống cần kiểm chứng

Để đảm bảo pipeline hoạt động đúng mục tiêu, cần kiểm tra một số tình huống có thể xảy ra trong thực tế:

- **Dependency có lỗ hổng:** SCA phát hiện thư viện không an toàn và cảnh báo trước khi triển khai.
- **Mã nguồn chứa lỗi bảo mật:** SAST phát hiện vấn đề trong quá trình build.
- **Ứng dụng có lỗ hổng khi chạy:** DAST và IAST hỗ trợ phát hiện vấn đề trong môi trường Staging.
- **Cấu hình AWS không an toàn:** AWS Config ghi nhận tài nguyên không đáp ứng yêu cầu cấu hình.
- **Deployment thất bại:** CloudWatch Logs hỗ trợ theo dõi và xác định nguyên nhân lỗi.
- **Phát hiện rủi ro bảo mật:** Security Hub tập trung các kết quả để DevOps và Security Team đánh giá và xử lý.

Những tình huống này giúp kiểm chứng khả năng phát hiện, cảnh báo và kiểm soát rủi ro của toàn bộ quy trình.

### What I Learned

Qua kiến trúc CI/CD tích hợp DevSecOps, tôi hiểu rõ hơn rằng bảo mật cần được xem là một phần của quá trình phát triển phần mềm, thay vì chỉ là bước kiểm tra cuối cùng trước khi phát hành.

Một số bài học quan trọng gồm:

- Tích hợp SCA và SAST ngay trong giai đoạn build để phát hiện sớm các vấn đề trong dependency và mã nguồn.
- Sử dụng DAST và IAST để kiểm tra ứng dụng trong môi trường đang chạy.
- Triển khai qua môi trường Staging trước khi đưa ứng dụng lên Production.
- Bổ sung Manual Approval để kiểm soát những thay đổi quan trọng trước khi phát hành.
- Kết hợp Security Hub, AWS Config và CloudTrail để tăng khả năng giám sát và kiểm soát bảo mật.
- Áp dụng IAM Least Privilege để hạn chế quyền truy cập không cần thiết.

Điểm quan trọng nhất là DevSecOps giúp chuyển hoạt động bảo mật từ việc kiểm tra sau triển khai sang việc kiểm tra liên tục trong toàn bộ vòng đời phát triển phần mềm.

Nhờ đó, doanh nghiệp có thể phát hiện sớm lỗ hổng, giảm thiểu rủi ro và nâng cao độ tin cậy của ứng dụng trước khi đưa vào môi trường Production.

### Images

Hình ảnh minh họa kiến trúc CI/CD Pipeline trên AWS với việc tích hợp các công cụ và dịch vụ DevSecOps nhằm kiểm tra, giám sát và kiểm soát bảo mật trước khi triển khai ứng dụng lên Production.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/aws-devsecops-cicd-pipeline.jpg" alt="Xây dựng CI/CD Pipeline trên AWS tích hợp DevSecOps" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Figure 1 - AWS CI/CD Pipeline integrated with DevSecOps security checks before Production deployment</em></p>
</div>

### References

1. AWS CodePipeline: https://docs.aws.amazon.com/codepipeline/
2. AWS CodeBuild: https://docs.aws.amazon.com/codebuild/
3. AWS CodeDeploy: https://docs.aws.amazon.com/codedeploy/
4. AWS Security Hub: https://docs.aws.amazon.com/securityhub/
5. AWS Config: https://docs.aws.amazon.com/config/
6. AWS CloudTrail: https://docs.aws.amazon.com/cloudtrail/
7. Amazon ECS: https://docs.aws.amazon.com/ecs/
