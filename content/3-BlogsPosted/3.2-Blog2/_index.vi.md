
---
title: "Blog 2"
date: 2026-11-24
weight: 2
chapter: false
pre: "<b> 3.2. </b>"
---

# AMAZON S3 – GIẢI PHÁP LƯU TRỮ VÀ BẢO MẬT DỮ LIỆU TRÊN AWS

Trong thời đại chuyển đổi số, dữ liệu đóng vai trò vô cùng quan trọng đối với hoạt động của các doanh nghiệp và hệ thống công nghệ thông tin. Từ website, ứng dụng di động đến các hệ thống trí tuệ nhân tạo, hầu hết các ứng dụng hiện đại đều cần một giải pháp lưu trữ dữ liệu an toàn, linh hoạt và có khả năng mở rộng.

Tuy nhiên, khi lượng dữ liệu ngày càng tăng, việc sử dụng những hệ thống lưu trữ truyền thống có thể gặp phải nhiều hạn chế như chi phí đầu tư phần cứng, giới hạn dung lượng, khả năng mở rộng và công việc bảo trì hệ thống.

Để giải quyết những vấn đề này, Amazon Web Services (AWS) cung cấp dịch vụ **Amazon Simple Storage Service (Amazon S3)**. Đây là một dịch vụ lưu trữ dữ liệu dạng đối tượng (Object Storage), cho phép người dùng lưu trữ và truy xuất dữ liệu với khả năng mở rộng linh hoạt.

Trong bài viết này, chúng ta sẽ cùng tìm hiểu Amazon S3 là gì, các lớp lưu trữ (Storage Classes), những tính năng quản lý và bảo mật dữ liệu quan trọng, cũng như cách ứng dụng S3 trong kiến trúc Data & Machine Learning trên AWS.

### 1. Amazon S3 là gì?

Amazon Simple Storage Service (Amazon S3) là dịch vụ lưu trữ dữ liệu dạng đối tượng do Amazon Web Services cung cấp.

Amazon S3 cho phép người dùng lưu trữ và truy xuất dữ liệu thông qua Internet, AWS Management Console, AWS CLI và các API được hỗ trợ mà không cần trực tiếp quản lý hạ tầng lưu trữ vật lý.

Dữ liệu được lưu trữ trên Amazon S3 có thể bao gồm:

- Hình ảnh và video.
- Tài liệu PDF, Word và Excel.
- Các tệp sao lưu dữ liệu.
- Bộ dữ liệu phục vụ Machine Learning và Artificial Intelligence.
- Các tệp tĩnh của website như HTML, CSS và JavaScript.
- Log hệ thống và dữ liệu phân tích.

Một trong những ưu điểm quan trọng của Amazon S3 là khả năng mở rộng theo nhu cầu lưu trữ. Thay vì phải đầu tư thêm ổ cứng hoặc máy chủ khi dung lượng dữ liệu tăng, người dùng có thể sử dụng hạ tầng lưu trữ do AWS quản lý và thanh toán dựa trên mức sử dụng thực tế.

Ngoài ra, S3 Standard được thiết kế với độ bền dữ liệu lên đến 99,999999999% (11 số 9). Đây là chỉ số về độ bền dữ liệu, không phải cam kết rằng dịch vụ luôn sẵn sàng 100%.

### 2. Những thành phần cơ bản trong Amazon S3

Để hiểu cách Amazon S3 hoạt động, chúng ta cần nắm được ba khái niệm quan trọng: Bucket, Object và Object Key.

**2.1. Bucket**

Bucket là vùng chứa được sử dụng để lưu trữ các Object trên Amazon S3.

Có thể hình dung Bucket như một khu vực lưu trữ riêng dành cho dữ liệu của một ứng dụng hoặc hệ thống.

Ví dụ, một ứng dụng quản lý hình ảnh có thể sử dụng Bucket với tên:

`my-image-storage-demo`

Bên trong Bucket này, người dùng có thể lưu trữ ảnh đại diện, ảnh sản phẩm, tài liệu và nhiều loại dữ liệu khác.

Khi tạo một S3 Bucket, người dùng cần lựa chọn AWS Region phù hợp dựa trên yêu cầu về vị trí dữ liệu và hệ thống.

**2.2. Object**

Object là đơn vị dữ liệu được lưu trữ trong Amazon S3.

Mỗi Object thường bao gồm dữ liệu thực tế của tệp và những thông tin mô tả liên quan (Metadata).

Ví dụ:

- `avatar.jpg`
- `report.pdf`
- `dataset.csv`
- `backup.zip`

Khác với một ổ đĩa truyền thống, Amazon S3 sử dụng mô hình Object Storage, trong đó dữ liệu được truy cập thông qua API và định danh Object.

**2.3. Object Key**

Object Key là tên định danh duy nhất của một Object trong Bucket.

Ví dụ:

`images/profile/avatar.jpg`

Ở đây, `images/profile/avatar.jpg` chính là Object Key.

Mặc dù tên này có cấu trúc giống đường dẫn thư mục, Amazon S3 chủ yếu sử dụng các tiền tố (Prefix) trong Object Key để tổ chức dữ liệu thay vì hệ thống thư mục vật lý truyền thống.

Điều này giúp người dùng dễ dàng phân loại, tìm kiếm và quản lý dữ liệu.

### 3. Các lớp lưu trữ Amazon S3 (Storage Classes)

Không phải dữ liệu nào cũng cần được truy cập với cùng tần suất.

Ví dụ, hình ảnh sản phẩm trên website có thể được truy cập hằng ngày, trong khi các tệp sao lưu từ nhiều năm trước chỉ được sử dụng khi cần khôi phục hệ thống.

Amazon S3 cung cấp nhiều Storage Classes nhằm đáp ứng những nhu cầu lưu trữ khác nhau.

**3.1. Phân cấp lưu trữ của Amazon S3**

Các lớp lưu trữ Amazon S3 có thể được phân nhóm dựa trên tần suất truy cập và yêu cầu truy xuất dữ liệu:

- **Frequently Accessed:** Dữ liệu được truy cập thường xuyên và cần độ trễ thấp.
- **Infrequently Accessed:** Dữ liệu ít được truy cập nhưng vẫn cần khả năng truy xuất nhanh khi cần.
- **Archive:** Dữ liệu được lưu trữ dài hạn, ít khi truy cập và có thể chấp nhận thời gian khôi phục lâu hơn.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/s3-storage-hierarchy.png" alt="Phân cấp lưu trữ của Amazon S3" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Hình 1 - Phân cấp lưu trữ của Amazon S3 dựa trên nhu cầu truy cập dữ liệu.</em></p>
</div>

**3.2. Tổng quan 8 lớp lưu trữ Amazon S3**

Amazon S3 cung cấp nhiều Storage Classes để người dùng lựa chọn tùy theo nhu cầu sử dụng.

| Storage Class | Đặc điểm | Trường hợp sử dụng |
|---|---|---|
| S3 Standard | Phù hợp dữ liệu thường xuyên truy cập | Website, hình ảnh, dữ liệu ứng dụng |
| S3 Intelligent-Tiering | Tự động tối ưu tầng lưu trữ dựa trên hành vi truy cập | Dữ liệu có tần suất truy cập khó dự đoán |
| S3 Standard-IA | Dữ liệu ít truy cập nhưng cần truy xuất nhanh | Backup và dữ liệu lưu trữ dài hạn |
| S3 One Zone-IA | Lưu trữ tại một Availability Zone | Dữ liệu có thể tái tạo |
| S3 Glacier Instant Retrieval | Lưu trữ dữ liệu ít truy cập nhưng vẫn cần truy xuất nhanh | Hình ảnh và hồ sơ lưu trữ dài hạn |
| S3 Glacier Flexible Retrieval | Lưu trữ dài hạn với thời gian khôi phục linh hoạt | Backup và dữ liệu lưu trữ định kỳ |
| S3 Glacier Deep Archive | Phù hợp dữ liệu rất ít truy cập, lưu trữ nhiều năm | Hồ sơ lịch sử và dữ liệu lưu trữ lâu dài |
| S3 Express One Zone | Lưu trữ hiệu suất cao trong một Availability Zone | Ứng dụng yêu cầu độ trễ truy cập rất thấp |

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/s3-storage-classes.png" alt="Tổng quan 8 lớp lưu trữ Amazon S3" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Hình 2 - Tổng quan 8 lớp lưu trữ Amazon S3 và các trường hợp sử dụng phổ biến.</em></p>
</div>

Một số lưu ý khi lựa chọn Storage Class:

- S3 Standard phù hợp với dữ liệu được truy cập thường xuyên.
- S3 Intelligent-Tiering phù hợp khi không thể dự đoán chính xác tần suất truy cập.
- S3 Standard-IA và One Zone-IA phù hợp với dữ liệu ít truy cập nhưng vẫn cần truy xuất nhanh.
- S3 Glacier Instant Retrieval phù hợp với dữ liệu lưu trữ dài hạn nhưng vẫn cần truy cập ngay.
- S3 Glacier Flexible Retrieval và Deep Archive phù hợp với dữ liệu lưu trữ lâu dài, có thể chấp nhận thời gian khôi phục lâu hơn.
- S3 Express One Zone phù hợp với ứng dụng cần độ trễ truy cập dữ liệu rất thấp.

Việc lựa chọn Storage Class phù hợp có thể giúp tối ưu chi phí. Tuy nhiên, cần xem xét thêm phí truy xuất, phí request, thời gian lưu trữ tối thiểu và thời gian khôi phục dữ liệu.

Đặc biệt, S3 One Zone-IA và S3 Express One Zone lưu trữ dữ liệu trong một Availability Zone duy nhất. Vì vậy, cần đánh giá yêu cầu về khả năng sẵn sàng và chịu lỗi trước khi sử dụng.

### 4. Những tính năng quan trọng của Amazon S3

Bên cạnh khả năng lưu trữ, Amazon S3 còn cung cấp nhiều tính năng giúp quản lý vòng đời dữ liệu và tăng cường bảo mật.

**4.1. S3 Versioning**

S3 Versioning là tính năng cho phép lưu giữ nhiều phiên bản khác nhau của một Object trong cùng Bucket.

Ví dụ, chúng ta có một tệp:

`project-report.pdf`

Sau khi cập nhật báo cáo, người dùng tải lên phiên bản mới với cùng Object Key.

Khi Versioning được bật, S3 có thể lưu giữ cả phiên bản cũ và phiên bản mới.

Tính năng này đặc biệt hữu ích khi:

- Vô tình ghi đè dữ liệu.
- Xóa nhầm một Object.
- Cần khôi phục phiên bản trước đó.
- Muốn theo dõi những thay đổi của dữ liệu.

Tuy nhiên, những phiên bản cũ vẫn có thể phát sinh chi phí lưu trữ. Vì vậy, nên kết hợp Versioning với Lifecycle Rules để quản lý dữ liệu hiệu quả.

**4.2. S3 Lifecycle Rules**

S3 Lifecycle Rules cho phép tự động quản lý vòng đời của Object dựa trên những quy tắc được thiết lập trước.

Ví dụ, một hệ thống lưu trữ Log có thể sử dụng chính sách:

- Trong 30 ngày đầu: Lưu dữ liệu ở S3 Standard.
- Sau 30 ngày: Chuyển dữ liệu sang Storage Class phù hợp với nhu cầu truy cập thấp hơn.
- Khi hết thời hạn lưu giữ: Tự động xóa dữ liệu theo chính sách đã cấu hình.

Thông qua Lifecycle Rules, doanh nghiệp có thể giảm công việc quản lý thủ công và tối ưu chi phí lưu trữ.

**4.3. S3 Encryption**

Bảo mật dữ liệu là một trong những yếu tố quan trọng nhất khi sử dụng Cloud Storage.

Amazon S3 hỗ trợ mã hóa dữ liệu nhằm bảo vệ thông tin khi được lưu trữ (Encryption at Rest).

Một số phương thức mã hóa phổ biến bao gồm:

- **SSE-S3:** Amazon S3 tự quản lý khóa mã hóa. Đây là phương thức mặc định đối với các Object mới được tải lên S3.
- **SSE-KMS:** Sử dụng AWS Key Management Service (AWS KMS) để quản lý khóa mã hóa và cung cấp thêm khả năng kiểm soát.
- **SSE-C:** Người dùng cung cấp khóa mã hóa trong các request, trong khi Amazon S3 thực hiện quá trình mã hóa và giải mã.

Việc lựa chọn phương thức mã hóa phù hợp phụ thuộc vào yêu cầu bảo mật và chính sách quản lý khóa của tổ chức.

**4.4. S3 Block Public Access**

Một trong những rủi ro bảo mật thường gặp khi sử dụng Cloud Storage là vô tình cho phép truy cập công khai đối với dữ liệu riêng tư.

Amazon S3 cung cấp tính năng Block Public Access nhằm ngăn chặn những cấu hình có thể khiến Bucket hoặc Object bị truy cập công khai ngoài ý muốn.

Tính năng này hỗ trợ kiểm soát:

- Public ACLs.
- Public Bucket Policies.
- Các cấu hình có thể cho phép truy cập công khai.

Đối với những Bucket mới, các thiết lập Block Public Access được bật mặc định.

**Khuyến nghị:** Nên giữ Block Public Access được bật trừ khi có yêu cầu cụ thể và đã đánh giá đầy đủ rủi ro bảo mật.

Đối với ứng dụng cần cung cấp hình ảnh hoặc dữ liệu cho người dùng bên ngoài, có thể cân nhắc Amazon CloudFront kết hợp Origin Access Control hoặc Presigned URLs tùy trường hợp.

### 5. Hướng dẫn cơ bản: Tạo và quản lý Amazon S3 Bucket

Sau khi tìm hiểu lý thuyết, chúng ta có thể thực hành tạo Bucket và tải dữ liệu lên Amazon S3.

**Yêu cầu:** Có tài khoản hoặc môi trường AWS được cấp quyền sử dụng Amazon S3.

**Bước 1: Truy cập AWS Management Console**

- Đăng nhập AWS Management Console.
- Tìm kiếm dịch vụ Amazon S3.
- Chọn mục Buckets để xem danh sách Bucket hiện có.

**Bước 2: Tạo S3 Bucket**

Chọn Create bucket và nhập các thông tin cần thiết:

- **Bucket name:** Đặt tên duy nhất theo quy tắc của S3.
- **AWS Region:** Chọn khu vực lưu trữ phù hợp.
- **Object Ownership:** Có thể giữ thiết lập mặc định.
- **Block Public Access:** Giữ bật để hạn chế truy cập công khai.
- **Versioning:** Có thể bật để tìm hiểu khả năng lưu trữ nhiều phiên bản.

Sau khi kiểm tra cấu hình, chọn Create bucket.

**Bước 3: Upload dữ liệu**

- Mở Bucket vừa tạo.
- Chọn Upload.
- Chọn một tệp thử nghiệm không chứa dữ liệu cá nhân hoặc thông tin nhạy cảm, chẳng hạn `demo.txt`.
- Chọn Upload để bắt đầu quá trình tải lên.

Sau khi tải lên thành công, Object sẽ xuất hiện trong danh sách của Bucket.

**Bước 4: Kiểm tra thông tin Object**

Chọn Object đã tải lên để xem:

- Object Key.
- Object Size.
- Storage Class.
- Metadata.
- Encryption.
- Version ID nếu Versioning được bật.

**Bước 5: Kiểm tra quyền truy cập**

Nếu Bucket đang bật Block Public Access, việc có Object URL không đồng nghĩa với việc mọi người trên Internet đều có thể truy cập dữ liệu.

Người dùng cần có quyền phù hợp thông qua IAM Policies, Bucket Policies hoặc những cơ chế truy cập được cấp phép khác.

Đây là một điểm quan trọng cần ghi nhớ khi xây dựng ứng dụng sử dụng Amazon S3.

**Bước 6: Dọn dẹp tài nguyên thử nghiệm**

Sau khi hoàn thành thực hành:

- Xóa những Object thử nghiệm không còn sử dụng.
- Kiểm tra các phiên bản cũ nếu Versioning được bật.
- Kiểm tra Delete Markers.
- Xóa Bucket sau khi đã làm trống hoàn toàn.

Việc dọn dẹp giúp hạn chế những chi phí lưu trữ không cần thiết.

**Lưu ý:** Chỉ thực hiện các thao tác này trong môi trường AWS được cấp quyền và cần kiểm tra kỹ dữ liệu trước khi xóa.

### 6. Ứng dụng thực tế: Amazon S3 trong kiến trúc Data & Machine Learning

Ngoài những ứng dụng lưu trữ thông thường, Amazon S3 còn đóng vai trò quan trọng trong các hệ thống xử lý dữ liệu và Machine Learning.

Ví dụ, một doanh nghiệp muốn xây dựng hệ thống AI có khả năng nhận diện và phân loại hình ảnh.

Trong trường hợp này, Amazon S3 có thể được sử dụng để lưu trữ dữ liệu đầu vào, bộ dữ liệu huấn luyện, mô hình và kết quả xử lý.

Cấu trúc dữ liệu mẫu có thể được tổ chức như sau:

```text
my-ai-dataset/
|
|-- raw-data/
|   |-- image_001.jpg
|   |-- image_002.jpg
|
|-- processed-data/
|   |-- image_001_processed.jpg
|
|-- train/
|   |-- training-data.csv
|
|-- validation/
|   |-- validation-data.csv
|
|-- models/
|   |-- model_v1.pth
|
|-- results/
    |-- predictions.csv
```

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/aws-data-ml-architecture.png" alt="Kiến trúc Data và Machine Learning trên AWS Cloud" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Hình 3 - Kiến trúc Data & Machine Learning trên AWS Cloud sử dụng Amazon S3 để lưu trữ và quản lý dữ liệu.</em></p>
</div>

Trong kiến trúc này, các thành phần có thể phối hợp với nhau như sau:

- **Amazon S3:** Lưu trữ dữ liệu gốc, dữ liệu đã xử lý, bộ dữ liệu huấn luyện và kết quả đầu ra.
- **AWS Glue:** Hỗ trợ khám phá, chuẩn bị và xử lý dữ liệu.
- **Amazon SageMaker:** Hỗ trợ xây dựng, huấn luyện và triển khai mô hình Machine Learning.
- **AWS Lambda:** Có thể kích hoạt các tác vụ xử lý khi có Object mới được tải lên S3.
- **Amazon CloudWatch:** Giám sát hoạt động hệ thống và trạng thái của các thành phần.

Ví dụ, khi người dùng tải một hình ảnh mới lên S3, một sự kiện có thể kích hoạt AWS Lambda để bắt đầu quá trình xử lý dữ liệu. Dữ liệu sau khi xử lý có thể được sử dụng trong quy trình huấn luyện hoặc dự đoán bằng Amazon SageMaker.

Sau khi hoàn thành, mô hình và kết quả dự đoán có thể được lưu trở lại Amazon S3 để phục vụ việc đánh giá và sử dụng trong tương lai.

Cần lưu ý rằng Amazon S3 không trực tiếp thực hiện quá trình huấn luyện mô hình AI. S3 đóng vai trò lưu trữ, trong khi các tác vụ xử lý và huấn luyện được thực hiện bởi những dịch vụ tính toán phù hợp.

### 7. Những lưu ý khi sử dụng Amazon S3

Để sử dụng Amazon S3 hiệu quả, chúng ta cần quan tâm đến một số vấn đề sau:

**Bảo mật dữ liệu:**

- Không công khai Bucket chứa dữ liệu riêng tư.
- Áp dụng nguyên tắc Least Privilege khi cấp quyền IAM.
- Sử dụng Encryption để bảo vệ dữ liệu.
- Thường xuyên kiểm tra Bucket Policies và Block Public Access.

**Tối ưu chi phí:**

- Lựa chọn Storage Class dựa trên tần suất truy cập thực tế.
- Sử dụng Lifecycle Rules để tự động chuyển đổi lớp lưu trữ.
- Theo dõi phí request, truy xuất và truyền dữ liệu.
- Kiểm tra những phiên bản Object cũ khi Versioning được bật.

**Quản lý dữ liệu:**

- Tổ chức Object Key theo cấu trúc tên rõ ràng.
- Bật Versioning khi cần khả năng khôi phục dữ liệu.
- Thiết lập chính sách lưu giữ và xóa dữ liệu phù hợp.

**Thiết kế hệ thống:**

- Lựa chọn AWS Region phù hợp.
- Xác định yêu cầu về độ trễ và khả năng sẵn sàng.
- Tích hợp Amazon S3 với những dịch vụ AWS khác khi xây dựng hệ thống Data & AI.

### 8. Những điều tôi học được (What I Learned)

Thông qua việc tìm hiểu Amazon S3, tôi hiểu rõ hơn vai trò của Cloud Storage trong việc xây dựng và vận hành những hệ thống công nghệ hiện đại.

Một số kiến thức quan trọng tôi học được bao gồm:

- Hiểu cách Amazon S3 tổ chức dữ liệu thông qua Bucket, Object và Object Key.
- Phân biệt các Storage Classes và lựa chọn lớp lưu trữ dựa trên nhu cầu truy cập.
- Hiểu cách Versioning hỗ trợ khôi phục dữ liệu khi xảy ra sự cố ngoài ý muốn.
- Sử dụng Lifecycle Rules để tự động quản lý vòng đời dữ liệu và tối ưu chi phí.
- Hiểu vai trò của Encryption và Block Public Access trong việc bảo vệ dữ liệu.
- Biết cách tạo Bucket, tải Object và kiểm tra thông tin dữ liệu thông qua AWS Management Console.
- Hiểu cách Amazon S3 được tích hợp trong kiến trúc Data & Machine Learning.

Bài học quan trọng nhất tôi rút ra được là việc lựa chọn một dịch vụ lưu trữ không đơn giản chỉ là tìm nơi để chứa dữ liệu. Chúng ta còn cần quan tâm đến cách dữ liệu được truy cập, bảo vệ, quản lý và tối ưu trong suốt vòng đời của nó.

Amazon S3 là một dịch vụ nền tảng quan trọng giúp xây dựng kiến thức về Cloud Computing và tiếp cận những kiến trúc AWS phức tạp hơn.

### 9. Kết luận

Amazon S3 là một trong những dịch vụ lưu trữ nền tảng và phổ biến của Amazon Web Services.

Với mô hình Object Storage, khả năng mở rộng, nhiều Storage Classes và các tính năng như Versioning, Lifecycle Rules, Encryption và Block Public Access, Amazon S3 cung cấp giải pháp linh hoạt cho nhiều nhu cầu khác nhau, từ dữ liệu ứng dụng thường xuyên truy cập đến những bộ dữ liệu cần lưu trữ trong nhiều năm.

Thông qua việc tìm hiểu và thực hành với Amazon S3, chúng ta có thể hiểu rõ hơn cách dữ liệu được tổ chức, lưu trữ, quản lý và bảo vệ trong môi trường Cloud Computing.

**Câu hỏi thảo luận:** Khi thiết kế một hệ thống lưu trữ lượng dữ liệu lớn, chúng ta nên dựa vào những yếu tố nào để lựa chọn giữa S3 Standard, S3 Intelligent-Tiering và các lớp lưu trữ S3 Glacier?

Rất mong được trao đổi và học hỏi thêm kinh nghiệm từ cộng đồng AWS Study Group!

### 10. Tài liệu tham khảo (References)

1. AWS Documentation – What is Amazon S3?
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html

2. AWS Documentation – Amazon S3 Storage Classes
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html

3. AWS Documentation – Managing the Lifecycle of Objects
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html

4. AWS Documentation – Using Versioning in S3 Buckets
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html

5. AWS Documentation – Protecting Data with Encryption
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingEncryption.html

6. AWS Documentation – Blocking Public Access to Your Amazon S3 Storage
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html

7. AWS Documentation – Amazon SageMaker
   https://docs.aws.amazon.com/sagemaker/
