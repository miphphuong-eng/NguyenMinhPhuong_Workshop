
---
title: "Blog 2"
date: 2026-11-24
weight: 2
chapter: false
pre: "<b> 3.2. </b>"
---

# AMAZON S3 – GIẢI PHÁP LƯU TRỮ VÀ BẢO MẬT DỮ LIỆU TRÊN AWS

Trong thời đại chuyển đổi số, dữ liệu đóng vai trò thiết yếu trong hoạt động của doanh nghiệp và các hệ thống công nghệ thông tin hiện đại. Từ website, ứng dụng di động cho đến các hệ thống Trí tuệ nhân tạo (AI), hầu hết các ứng dụng ngày nay đều cần một giải pháp lưu trữ an toàn, linh hoạt và có khả năng mở rộng.

Tuy nhiên, khi lượng dữ liệu ngày càng tăng, các hệ thống lưu trữ truyền thống có thể gặp nhiều thách thức như chi phí đầu tư phần cứng, giới hạn dung lượng, khó khăn trong việc mở rộng và chi phí bảo trì hạ tầng.

Để giải quyết những vấn đề này, Amazon Web Services (AWS) cung cấp **Amazon Simple Storage Service (Amazon S3)**. Đây là dịch vụ lưu trữ đối tượng (Object Storage), cho phép người dùng lưu trữ và truy xuất dữ liệu với khả năng mở rộng linh hoạt.

Trong bài viết này, chúng ta sẽ tìm hiểu Amazon S3 là gì, các lớp lưu trữ (Storage Classes), những tính năng quan trọng trong quản lý và bảo mật dữ liệu, cũng như cách S3 được ứng dụng trong kiến trúc Data & Machine Learning trên AWS.

### 1. Amazon S3 là gì?

Amazon Simple Storage Service (Amazon S3) là dịch vụ lưu trữ đối tượng được cung cấp bởi Amazon Web Services.

Amazon S3 cho phép người dùng lưu trữ và truy xuất dữ liệu thông qua Internet, AWS Management Console, AWS CLI và các API được hỗ trợ mà không cần trực tiếp quản lý hạ tầng lưu trữ vật lý.

Dữ liệu được lưu trữ trên Amazon S3 có thể bao gồm:

- Hình ảnh và video.
- Tài liệu PDF, Word và Excel.
- Các tệp sao lưu dữ liệu (Backup).
- Bộ dữ liệu phục vụ Machine Learning và Artificial Intelligence.
- Tệp website tĩnh như HTML, CSS và JavaScript.
- Log hệ thống và dữ liệu phục vụ phân tích.

Một trong những ưu điểm nổi bật của Amazon S3 là khả năng mở rộng theo nhu cầu lưu trữ. Thay vì phải mua thêm ổ cứng hoặc máy chủ khi dung lượng dữ liệu tăng lên, người dùng có thể sử dụng hạ tầng lưu trữ do AWS quản lý và thanh toán dựa trên mức sử dụng thực tế.

Ngoài ra, S3 Standard được thiết kế để cung cấp độ bền dữ liệu (Data Durability) lên đến 99.999999999% (11 số 9). Đây là chỉ số về độ bền dữ liệu, không phải cam kết dịch vụ luôn sẵn sàng 100%.

### 2. Các thành phần cơ bản của Amazon S3

Để hiểu cách Amazon S3 hoạt động, chúng ta cần nắm rõ ba khái niệm quan trọng: Bucket, Object và Object Key.

**2.1. Bucket**

Bucket là một vùng chứa được sử dụng để lưu trữ các Object trong Amazon S3.

Có thể hiểu Bucket giống như một khu vực lưu trữ riêng dành cho dữ liệu của một ứng dụng hoặc hệ thống.

Ví dụ, một ứng dụng quản lý hình ảnh có thể sử dụng Bucket với tên:

`my-image-storage-demo`

Bên trong Bucket này, người dùng có thể lưu trữ ảnh đại diện, hình ảnh sản phẩm, tài liệu và nhiều loại dữ liệu khác.

Khi tạo một S3 Bucket, người dùng cần lựa chọn AWS Region phù hợp với vị trí lưu trữ dữ liệu và yêu cầu của hệ thống.

**2.2. Object**

Object là một đơn vị dữ liệu riêng lẻ được lưu trữ trong Amazon S3.

Mỗi Object thường bao gồm dữ liệu thực tế của tệp và các thông tin mô tả liên quan (Metadata).

Một số ví dụ:

- `avatar.jpg`
- `report.pdf`
- `dataset.csv`
- `backup.zip`

Khác với hệ thống lưu trữ dựa trên ổ đĩa truyền thống, Amazon S3 sử dụng mô hình Object Storage, trong đó dữ liệu được truy cập thông qua API và các định danh Object.

**2.3. Object Key**

Object Key là định danh duy nhất của một Object bên trong một Bucket.

Ví dụ:

`images/profile/avatar.jpg`

Trong trường hợp này, `images/profile/avatar.jpg` chính là Object Key.

Mặc dù cấu trúc đặt tên này trông giống đường dẫn thư mục truyền thống, Amazon S3 chủ yếu sử dụng các tiền tố (Prefix) trong Object Key để tổ chức dữ liệu thay vì cấu trúc thư mục vật lý như trên máy tính.

Điều này giúp người dùng dễ dàng phân loại, tìm kiếm và quản lý dữ liệu.

### 3. Các lớp lưu trữ của Amazon S3 (Storage Classes)

Không phải tất cả dữ liệu đều cần được truy cập với tần suất giống nhau.

Ví dụ, hình ảnh sản phẩm trên website có thể được truy cập mỗi ngày, trong khi các tệp sao lưu từ nhiều năm trước chỉ được sử dụng khi hệ thống cần khôi phục.

Amazon S3 cung cấp nhiều lớp lưu trữ (Storage Classes) để đáp ứng những nhu cầu sử dụng dữ liệu khác nhau.

**3.1. Phân cấp lưu trữ của Amazon S3**

Các Storage Classes của Amazon S3 có thể được phân nhóm dựa trên tần suất truy cập và yêu cầu truy xuất dữ liệu:

- **Frequently Accessed (Truy cập thường xuyên):** Dành cho dữ liệu được sử dụng thường xuyên và yêu cầu độ trễ truy cập thấp.
- **Infrequently Accessed (Truy cập không thường xuyên):** Dành cho dữ liệu ít được sử dụng hơn nhưng vẫn cần truy xuất nhanh khi cần thiết.
- **Archive (Lưu trữ dài hạn):** Dành cho dữ liệu ít khi truy cập và có thể chấp nhận thời gian khôi phục lâu hơn.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/s3-storage-hierarchy.png" alt="Phân cấp lưu trữ Amazon S3" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Hình 1 - Phân cấp các lớp lưu trữ Amazon S3 dựa trên nhu cầu truy cập dữ liệu.</em></p>
</div>

**3.2. Tổng quan về 8 lớp lưu trữ Amazon S3**

Amazon S3 cung cấp nhiều lớp lưu trữ khác nhau để người dùng lựa chọn tùy theo nhu cầu sử dụng.

| Storage Class | Đặc điểm | Trường hợp sử dụng phổ biến |
|---|---|---|
| S3 Standard | Thiết kế cho dữ liệu được truy cập thường xuyên | Website, hình ảnh, dữ liệu ứng dụng |
| S3 Intelligent-Tiering | Tự động tối ưu lớp lưu trữ dựa trên mô hình truy cập dữ liệu | Dữ liệu có tần suất truy cập khó dự đoán |
| S3 Standard-IA | Dữ liệu ít truy cập nhưng vẫn cần truy xuất nhanh | Dữ liệu Backup và lưu trữ dài hạn |
| S3 One Zone-IA | Lưu trữ dữ liệu trong một Availability Zone | Dữ liệu có thể tái tạo khi cần |
| S3 Glacier Instant Retrieval | Dữ liệu ít truy cập nhưng vẫn cần truy xuất nhanh | Hình ảnh và hồ sơ lưu trữ dài hạn |
| S3 Glacier Flexible Retrieval | Lưu trữ dài hạn với thời gian truy xuất linh hoạt | Backup và dữ liệu lưu trữ định kỳ |
| S3 Glacier Deep Archive | Dành cho dữ liệu rất ít truy cập, cần lưu trữ trong nhiều năm | Hồ sơ lịch sử và dữ liệu lưu trữ dài hạn |
| S3 Express One Zone | Lưu trữ hiệu năng cao trong một Availability Zone | Ứng dụng yêu cầu độ trễ truy cập dữ liệu rất thấp |

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/s3-storage-classes.png" alt="Tổng quan 8 lớp lưu trữ Amazon S3" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Hình 2 - Tổng quan tám lớp lưu trữ Amazon S3 và các trường hợp sử dụng phổ biến.</em></p>
</div>

Một số lưu ý quan trọng khi lựa chọn Storage Class:

- S3 Standard phù hợp với dữ liệu được truy cập thường xuyên.
- S3 Intelligent-Tiering hữu ích khi không thể dự đoán chính xác tần suất truy cập dữ liệu.
- S3 Standard-IA và One Zone-IA phù hợp với dữ liệu ít truy cập nhưng vẫn cần truy xuất nhanh.
- S3 Glacier Instant Retrieval phù hợp với dữ liệu lưu trữ dài hạn nhưng vẫn cần truy cập gần như ngay lập tức.
- S3 Glacier Flexible Retrieval và Deep Archive phù hợp với dữ liệu lưu trữ dài hạn, có thể chấp nhận thời gian truy xuất lâu hơn.
- S3 Express One Zone phù hợp với các ứng dụng yêu cầu độ trễ truy cập dữ liệu rất thấp.

Việc lựa chọn Storage Class phù hợp có thể giúp tối ưu chi phí. Tuy nhiên, người dùng cũng cần cân nhắc phí truy xuất dữ liệu, phí yêu cầu API, thời gian lưu trữ tối thiểu và yêu cầu khôi phục dữ liệu.

Đặc biệt, S3 One Zone-IA và S3 Express One Zone lưu trữ dữ liệu trong một Availability Zone duy nhất. Vì vậy, cần đánh giá kỹ yêu cầu về tính sẵn sàng và khả năng chịu lỗi trước khi sử dụng hai lớp lưu trữ này.

### 4. Những tính năng quan trọng của Amazon S3

Ngoài khả năng lưu trữ, Amazon S3 còn cung cấp nhiều tính năng hỗ trợ quản lý vòng đời dữ liệu và tăng cường bảo mật.

**4.1. S3 Versioning**

S3 Versioning là tính năng cho phép lưu trữ nhiều phiên bản của cùng một Object trong một Bucket.

Ví dụ, một tệp có tên:

`project-report.pdf`

Sau khi cập nhật nội dung báo cáo, người dùng tải lên phiên bản mới với cùng Object Key.

Khi Versioning được bật, S3 có thể giữ lại cả phiên bản cũ và phiên bản mới.

Tính năng này đặc biệt hữu ích trong các trường hợp:

- Dữ liệu bị ghi đè ngoài ý muốn.
- Object bị xóa nhầm.
- Cần khôi phục lại phiên bản trước đó.
- Cần theo dõi những thay đổi của dữ liệu đã lưu trữ.

Tuy nhiên, các phiên bản cũ vẫn có thể phát sinh chi phí lưu trữ. Vì vậy, nên kết hợp Versioning với Lifecycle Rules để quản lý dữ liệu hiệu quả hơn.

**4.2. S3 Lifecycle Rules**

S3 Lifecycle Rules cho phép người dùng tự động quản lý vòng đời của các Object dựa trên những quy tắc được thiết lập trước.

Ví dụ, một hệ thống lưu trữ log có thể áp dụng chính sách như sau:

- Trong 30 ngày đầu: Lưu trữ dữ liệu bằng S3 Standard.
- Sau 30 ngày: Chuyển dữ liệu sang Storage Class phù hợp với nhu cầu truy cập ít thường xuyên hơn.
- Sau khi hết thời hạn lưu trữ: Tự động xóa dữ liệu theo chính sách đã cấu hình.

Thông qua Lifecycle Rules, doanh nghiệp có thể giảm các thao tác quản lý thủ công và tối ưu chi phí lưu trữ.

**4.3. S3 Encryption**

Bảo mật dữ liệu là một trong những yếu tố quan trọng nhất khi sử dụng dịch vụ Cloud Storage.

Amazon S3 hỗ trợ mã hóa dữ liệu nhằm bảo vệ thông tin khi dữ liệu được lưu trữ (Encryption at Rest).

Một số phương thức mã hóa phổ biến bao gồm:

- **SSE-S3:** Amazon S3 quản lý khóa mã hóa. Đây là phương thức mã hóa mặc định đối với các Object mới được tải lên S3.
- **SSE-KMS:** Sử dụng AWS Key Management Service (AWS KMS) để quản lý khóa mã hóa và cung cấp thêm khả năng kiểm soát.
- **SSE-C:** Người dùng cung cấp khóa mã hóa trong các request, trong khi Amazon S3 thực hiện quá trình mã hóa và giải mã dữ liệu.

Phương thức mã hóa phù hợp sẽ phụ thuộc vào yêu cầu bảo mật và chính sách quản lý khóa của tổ chức.

**4.4. S3 Block Public Access**

Một trong những rủi ro bảo mật phổ biến khi sử dụng Cloud Storage là vô tình cho phép truy cập công khai vào dữ liệu riêng tư.

Amazon S3 cung cấp tính năng Block Public Access nhằm hạn chế những cấu hình có thể khiến Bucket hoặc Object bị công khai ngoài ý muốn.

Tính năng này hỗ trợ kiểm soát:

- Public ACLs.
- Public Bucket Policies.
- Những cấu hình có thể cho phép truy cập công khai.

Đối với các Bucket mới được tạo, các thiết lập Block Public Access được bật mặc định.

**Khuyến nghị:** Nên giữ Block Public Access luôn được bật, trừ khi có yêu cầu cụ thể và các rủi ro bảo mật liên quan đã được đánh giá đầy đủ.

Đối với các ứng dụng cần phân phối hình ảnh hoặc dữ liệu cho người dùng bên ngoài, có thể cân nhắc sử dụng Amazon CloudFront kết hợp Origin Access Control hoặc Presigned URLs.

### 5. Hướng dẫn cơ bản: Tạo và quản lý Amazon S3 Bucket

Sau khi tìm hiểu các khái niệm, chúng ta có thể thực hành tạo một Bucket và tải dữ liệu lên Amazon S3.

**Yêu cầu:** Có tài khoản AWS hoặc môi trường AWS được cấp quyền sử dụng Amazon S3.

**Bước 1: Truy cập AWS Management Console**

- Đăng nhập vào AWS Management Console.
- Tìm kiếm dịch vụ Amazon S3.
- Chọn mục Buckets để xem danh sách các Bucket hiện có.

**Bước 2: Tạo S3 Bucket**

Chọn Create bucket và nhập các thông tin cần thiết:

- **Bucket name:** Nhập tên duy nhất theo quy tắc đặt tên của S3.
- **AWS Region:** Chọn khu vực lưu trữ phù hợp.
- **Object Ownership:** Giữ thiết lập mặc định nếu không có yêu cầu đặc biệt.
- **Block Public Access:** Giữ trạng thái bật để tránh vô tình công khai dữ liệu.
- **Versioning:** Có thể bật tùy chọn này để tìm hiểu cách quản lý nhiều phiên bản Object.

Sau khi kiểm tra lại cấu hình, chọn Create bucket.

**Bước 3: Tải dữ liệu lên Bucket**

- Mở Bucket vừa tạo.
- Chọn Upload.
- Chọn một tệp thử nghiệm không chứa thông tin cá nhân hoặc dữ liệu nhạy cảm, ví dụ `demo.txt`.
- Chọn Upload để bắt đầu quá trình tải lên.

Sau khi tải lên thành công, Object sẽ xuất hiện trong danh sách dữ liệu của Bucket.

**Bước 4: Kiểm tra thông tin Object**

Chọn Object vừa tải lên để xem các thông tin:

- Object Key.
- Object Size.
- Storage Class.
- Metadata.
- Encryption.
- Version ID nếu Versioning được bật.

**Bước 5: Kiểm tra quyền truy cập**

Nếu Block Public Access được bật, việc có URL của Object không đồng nghĩa với việc mọi người trên Internet đều có thể truy cập dữ liệu.

Người dùng cần có quyền phù hợp thông qua IAM Policies, Bucket Policies hoặc các cơ chế truy cập được cấp phép khác.

Đây là một khái niệm quan trọng cần ghi nhớ khi phát triển ứng dụng sử dụng Amazon S3.

**Bước 6: Dọn dẹp tài nguyên thử nghiệm**

Sau khi hoàn thành thực hành:

- Xóa các Object thử nghiệm không còn cần thiết.
- Kiểm tra các phiên bản cũ nếu Versioning được bật.
- Kiểm tra Delete Markers.
- Xóa Bucket sau khi đã xóa toàn bộ dữ liệu bên trong.

Việc dọn dẹp tài nguyên giúp tránh phát sinh các chi phí lưu trữ không cần thiết.

**Lưu ý:** Chỉ thực hiện những thao tác này trong môi trường AWS được cấp quyền và cần kiểm tra kỹ dữ liệu trước khi xóa.

### 6. Ứng dụng thực tế: Amazon S3 trong kiến trúc Data & Machine Learning

Ngoài những ứng dụng lưu trữ thông thường, Amazon S3 còn đóng vai trò quan trọng trong các hệ thống xử lý dữ liệu và Machine Learning.

Ví dụ, một doanh nghiệp muốn xây dựng hệ thống AI có khả năng nhận diện và phân loại hình ảnh.

Trong trường hợp này, Amazon S3 có thể được sử dụng để lưu trữ dữ liệu đầu vào, bộ dữ liệu huấn luyện, mô hình và kết quả xử lý.

Một cấu trúc dữ liệu mẫu có thể được tổ chức như sau:

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

- **Amazon S3:** Lưu trữ dữ liệu thô, dữ liệu đã xử lý, bộ dữ liệu huấn luyện và kết quả đầu ra.
- **AWS Glue:** Hỗ trợ khám phá, chuẩn bị và xử lý dữ liệu.
- **Amazon SageMaker:** Hỗ trợ xây dựng, huấn luyện và triển khai các mô hình Machine Learning.
- **AWS Lambda:** Có thể kích hoạt các tác vụ xử lý khi có Object mới được tải lên S3.
- **Amazon CloudWatch:** Giám sát hoạt động hệ thống và trạng thái của các thành phần.

Ví dụ, khi người dùng tải một hình ảnh mới lên S3, một sự kiện có thể kích hoạt AWS Lambda để bắt đầu tác vụ xử lý dữ liệu. Dữ liệu sau khi xử lý có thể được sử dụng trong quy trình huấn luyện hoặc dự đoán bằng Amazon SageMaker.

Sau khi quá trình hoàn tất, mô hình và kết quả dự đoán có thể được lưu ngược lại Amazon S3 để phục vụ việc đánh giá và sử dụng trong tương lai.

Điều quan trọng cần hiểu là Amazon S3 không trực tiếp thực hiện quá trình huấn luyện mô hình AI. S3 cung cấp lớp lưu trữ dữ liệu, trong khi các tác vụ xử lý và huấn luyện được thực hiện bởi những dịch vụ tính toán phù hợp.

### 7. Những lưu ý quan trọng khi sử dụng Amazon S3

Để sử dụng Amazon S3 hiệu quả, cần quan tâm đến một số yếu tố sau:

**Bảo mật dữ liệu:**

- Tránh công khai các Bucket chứa dữ liệu riêng tư.
- Áp dụng nguyên tắc Least Privilege khi cấp quyền IAM.
- Sử dụng Encryption để bảo vệ dữ liệu được lưu trữ.
- Thường xuyên kiểm tra Bucket Policies và các thiết lập Block Public Access.

**Tối ưu chi phí:**

- Lựa chọn Storage Class dựa trên tần suất truy cập thực tế.
- Sử dụng Lifecycle Rules để tự động chuyển đổi lớp lưu trữ.
- Theo dõi chi phí request, retrieval và data transfer.
- Kiểm tra các phiên bản Object cũ khi Versioning được bật.

**Quản lý dữ liệu:**

- Tổ chức Object Keys theo cấu trúc đặt tên rõ ràng.
- Bật Versioning khi cần khả năng khôi phục dữ liệu.
- Thiết lập chính sách lưu trữ và xóa dữ liệu phù hợp.

**Thiết kế hệ thống:**

- Lựa chọn AWS Region phù hợp.
- Xác định yêu cầu về độ trễ và tính sẵn sàng.
- Tích hợp Amazon S3 với các dịch vụ AWS khác khi xây dựng hệ thống Data & AI.

### 8. Những điều tôi học được (What I Learned)

Thông qua việc tìm hiểu Amazon S3, tôi hiểu rõ hơn vai trò của Cloud Storage trong quá trình xây dựng và vận hành các hệ thống công nghệ hiện đại.

Một số bài học quan trọng bao gồm:

- Hiểu cách Amazon S3 tổ chức dữ liệu thông qua Bucket, Object và Object Key.
- Phân biệt các Storage Classes và lựa chọn lớp lưu trữ phù hợp với nhu cầu truy cập.
- Hiểu cách Versioning hỗ trợ khôi phục dữ liệu khi xảy ra sự cố ngoài ý muốn.
- Sử dụng Lifecycle Rules để tự động quản lý vòng đời dữ liệu và tối ưu chi phí lưu trữ.
- Hiểu vai trò của Encryption và Block Public Access trong việc bảo vệ dữ liệu.
- Biết cách tạo Bucket, tải Object và kiểm tra thông tin dữ liệu thông qua AWS Management Console.
- Hiểu cách Amazon S3 tích hợp trong kiến trúc Data & Machine Learning.

Bài học quan trọng nhất tôi rút ra được là lựa chọn một dịch vụ lưu trữ không chỉ đơn giản là tìm nơi để lưu dữ liệu. Chúng ta còn cần quan tâm đến cách dữ liệu được truy cập, bảo vệ, quản lý và tối ưu trong suốt vòng đời của nó.

Amazon S3 là một dịch vụ nền tảng quan trọng giúp xây dựng kiến thức về Cloud Computing và tìm hiểu những kiến trúc AWS nâng cao hơn.

### 9. Kết luận (Conclusion)

Amazon S3 là một trong những dịch vụ lưu trữ nền tảng được cung cấp bởi Amazon Web Services.

Với mô hình Object Storage, khả năng mở rộng, nhiều Storage Classes và các tính năng như Versioning, Lifecycle Rules, Encryption và Block Public Access, Amazon S3 có thể đáp ứng nhiều nhu cầu lưu trữ khác nhau, từ dữ liệu ứng dụng được truy cập thường xuyên đến các bộ dữ liệu cần được lưu trữ trong nhiều năm.

Thông qua việc tìm hiểu và thực hành với Amazon S3, chúng ta có thể hiểu rõ hơn cách dữ liệu được tổ chức, lưu trữ, quản lý và bảo vệ trong môi trường Cloud Computing.

**Câu hỏi thảo luận:** Khi thiết kế một hệ thống lưu trữ lượng dữ liệu lớn, chúng ta cần cân nhắc những yếu tố nào khi lựa chọn giữa S3 Standard, S3 Intelligent-Tiering và các lớp lưu trữ S3 Glacier?

Tôi rất mong được trao đổi ý kiến và học hỏi thêm từ cộng đồng AWS Study Group!

### 10. Tài liệu tham khảo (References)

1. AWS Documentation – Amazon S3 là gì?
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html

2. AWS Documentation – Các lớp lưu trữ Amazon S3
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html

3. AWS Documentation – Quản lý vòng đời của Object
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html

4. AWS Documentation – Sử dụng Versioning trong S3 Bucket
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html

5. AWS Documentation – Bảo vệ dữ liệu bằng Encryption
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingEncryption.html

6. AWS Documentation – Ngăn chặn truy cập công khai vào Amazon S3
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html

7. AWS Documentation – Amazon SageMaker
   https://docs.aws.amazon.com/sagemaker/
