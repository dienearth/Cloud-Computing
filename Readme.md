# STUDYFLOW — TỔNG QUAN ĐỒ ÁN

## Thiết kế và triển khai hệ thống quản lý nhiệm vụ và dự án cho sinh viên trên nền tảng đám mây AWS

- **Môn học:** Điện toán đám mây (Cloud Computing)
- **Tên hệ thống dự kiến:** StudyFlow
- **Lĩnh vực:** Quản lý dự án, quản lý nhiệm vụ và cộng tác học tập trên nền tảng Cloud
- **Nền tảng triển khai:** Amazon Web Services (AWS)
- **Mục đích tài liệu:** Thống nhất ý tưởng, xác định phạm vi chức năng, định hướng kiến trúc và kế hoạch triển khai đồ án.
- **Lưu ý:** Các chức năng, dịch vụ AWS và mô hình dữ liệu dưới đây là phương án đề xuất. Nhóm cần thống nhất với giảng viên trước khi xác định phạm vi chính thức.

---

## 1. Tóm tắt đề tài

StudyFlow là hệ thống quản lý nhiệm vụ và dự án dành cho sinh viên, được thiết kế và triển khai trên nền tảng điện toán đám mây AWS. Hệ thống hỗ trợ sinh viên tổ chức công việc học tập cá nhân, quản lý các dự án nhóm, phân công nhiệm vụ, theo dõi tiến độ thực hiện và trao đổi tài liệu trong quá trình làm việc.

Người dùng có thể tạo dự án, mời thành viên tham gia, thiết lập thời hạn hoàn thành, giao nhiệm vụ cho từng thành viên và cập nhật trạng thái công việc. Hệ thống cung cấp dashboard tổng quan giúp sinh viên theo dõi các nhiệm vụ sắp đến hạn, nhiệm vụ quá hạn, tiến độ của từng dự án và mức độ hoàn thành công việc của nhóm.

Các dịch vụ AWS được sử dụng để triển khai backend, lưu trữ dữ liệu, quản lý tài khoản, lưu trữ tệp tin và gửi thông báo. Nhờ triển khai trên Cloud, hệ thống có thể được truy cập thông qua Internet từ nhiều thiết bị mà không cần cài đặt một máy chủ riêng tại máy tính của nhóm.

StudyFlow tập trung vào việc quản lý công việc và hỗ trợ cộng tác trong học tập. Hệ thống không thay thế các nền tảng quản lý học tập của trường đại học và không mặc định bao gồm chức năng chấm điểm, quản lý điểm số hoặc tích hợp với hệ thống đào tạo chính thức.

## 2. Vấn đề thực tế và mục tiêu

### 2.1. Vấn đề thực tế

Trong quá trình học tập, sinh viên thường phải thực hiện nhiều bài tập cá nhân, bài tập nhóm, báo cáo môn học và đồ án cùng lúc. Việc sử dụng nhiều công cụ riêng lẻ như tin nhắn, bảng tính, lịch cá nhân hoặc tài liệu chia sẻ có thể dẫn đến một số vấn đề:

- Khó theo dõi toàn bộ nhiệm vụ cần hoàn thành và thời hạn nộp bài.
- Khó phân chia công việc rõ ràng giữa các thành viên trong nhóm.
- Không dễ xác định ai đang phụ trách nhiệm vụ nào và công việc đã hoàn thành đến đâu.
- Thông tin nhiệm vụ bị phân tán giữa nhiều nền tảng.
- Thành viên dễ bỏ lỡ thời hạn hoặc quên cập nhật tiến độ.
- Nhóm trưởng mất nhiều thời gian tổng hợp tình trạng công việc và đánh giá tiến độ dự án.

### 2.2. Mục tiêu của đề tài

1. Xây dựng hệ thống quản lý nhiệm vụ cá nhân và dự án nhóm dành cho sinh viên.
2. Cung cấp chức năng tạo, chỉnh sửa, phân công và theo dõi nhiệm vụ.
3. Hỗ trợ quản lý thành viên, vai trò và quyền truy cập trong từng dự án.
4. Theo dõi trạng thái, thời hạn và tiến độ hoàn thành của nhiệm vụ.
5. Hỗ trợ lưu trữ và quản lý tài liệu phục vụ quá trình thực hiện dự án.
6. Cung cấp dashboard trực quan để tổng hợp nhiệm vụ và tiến độ.
7. Triển khai backend và dữ liệu trên AWS nhằm thể hiện khả năng ứng dụng điện toán đám mây.
8. Đảm bảo dữ liệu được phân quyền truy cập, có khả năng mở rộng và quản lý chi phí phù hợp với quy mô đồ án.
9. Xây dựng kịch bản demo thực tế từ lúc tạo dự án đến khi hoàn thành nhiệm vụ và tổng hợp kết quả.

### 2.3. Phạm vi ngoài mục tiêu chính

Các chức năng sau chưa được mặc định là yêu cầu bắt buộc:

- Tích hợp hệ thống quản lý đào tạo của trường.
- Tự động chấm điểm bài tập hoặc báo cáo.
- Họp trực tuyến, gọi video hoặc nhắn tin thời gian thực.
- Trí tuệ nhân tạo tự động lập kế hoạch dự án.
- Quản lý tài chính, thanh toán hoặc thu phí người dùng.
- Triển khai đa vùng AWS hoặc xây dựng hệ thống phân tán phức tạp.

Nhóm chỉ nên bổ sung các chức năng này nếu phạm vi cơ bản đã hoàn thành và còn đủ thời gian.

## 3. Các chức năng của hệ thống

### 3.1. Quản lý tài khoản người dùng

- Đăng ký tài khoản sinh viên.
- Đăng nhập và đăng xuất.
- Quản lý thông tin cá nhân như họ tên, email và ảnh đại diện.
- Cập nhật thông tin tài khoản.
- Phân biệt quyền truy cập giữa thành viên, trưởng nhóm và quản trị viên nếu hệ thống cần vai trò quản trị toàn cục.
- Kiểm tra quyền trước khi cho phép người dùng đọc hoặc thay đổi dữ liệu.

**Đề xuất:** Sử dụng Amazon Cognito để xác thực người dùng và quản lý phiên đăng nhập.

### 3.2. Quản lý dự án

- Tạo dự án mới với tên, mô tả, ngày bắt đầu và thời hạn dự kiến.
- Chỉnh sửa thông tin dự án.
- Xem danh sách dự án mà người dùng tham gia.
- Xem chi tiết từng dự án.
- Mời thành viên tham gia dự án bằng email hoặc mã mời.
- Thêm, xóa thành viên theo quyền được cấp.
- Chỉ định trưởng nhóm và thành viên phụ trách.
- Cập nhật trạng thái dự án như `PLANNING`, `IN_PROGRESS`, `COMPLETED` hoặc `ARCHIVED`.
- Theo dõi tỷ lệ hoàn thành nhiệm vụ của dự án.

Quyền quản lý dự án thuộc về trưởng nhóm hoặc người được cấp quyền phù hợp.

### 3.3. Quản lý nhiệm vụ

- Tạo nhiệm vụ thuộc một dự án hoặc nhiệm vụ cá nhân.
- Nhập tên, mô tả, mức độ ưu tiên và thời hạn hoàn thành.
- Giao nhiệm vụ cho một thành viên.
- Chỉnh sửa thông tin nhiệm vụ.
- Cập nhật trạng thái nhiệm vụ.
- Xem danh sách nhiệm vụ theo người phụ trách.
- Lọc nhiệm vụ theo dự án, trạng thái, mức độ ưu tiên và thời hạn.
- Tìm kiếm nhiệm vụ theo tên hoặc từ khóa.
- Hiển thị các nhiệm vụ sắp đến hạn và đã quá hạn.
- Ghi nhận thời điểm tạo, cập nhật và hoàn thành nhiệm vụ.

Các trạng thái nhiệm vụ đề xuất:

- `TODO`: Chưa thực hiện.
- `IN_PROGRESS`: Đang thực hiện.
- `REVIEW`: Chờ xem xét hoặc kiểm tra.
- `DONE`: Đã hoàn thành.

Trạng thái `REVIEW` có thể được bỏ khỏi phiên bản đầu tiên nếu nhóm muốn đơn giản hóa quy trình.

### 3.4. Quản lý thành viên và cộng tác

- Xem danh sách thành viên của dự án.
- Xem các nhiệm vụ được giao cho từng thành viên.
- Cho phép trưởng nhóm phân công hoặc thay đổi người phụ trách.
- Theo dõi số lượng nhiệm vụ đã hoàn thành và đang thực hiện.
- Ghi nhận lịch sử thay đổi nhiệm vụ ở mức cơ bản.
- Hiển thị thông tin cần thiết để nhóm trưởng theo dõi tiến độ.

Chức năng cộng tác trong phiên bản đầu tiên tập trung vào nhiệm vụ, phân công và trạng thái công việc; không yêu cầu xây dựng hệ thống chat riêng.

### 3.5. Quản lý tài liệu

- Tải lên tệp phục vụ dự án như PDF, DOCX, PPTX hoặc hình ảnh.
- Liên kết tài liệu với dự án hoặc nhiệm vụ.
- Hiển thị tên tệp, người tải lên và thời điểm tải lên.
- Cho phép người có quyền tải xuống tài liệu.
- Xóa hoặc thay thế tệp theo quyền được cấp.

**Đề xuất:** Sử dụng Amazon S3 để lưu trữ tệp và lưu thông tin mô tả tệp trong cơ sở dữ liệu.

Nhóm cần giới hạn dung lượng, loại tệp được phép tải lên và kiểm soát quyền truy cập. Không để các tệp riêng tư được công khai chỉ vì thuận tiện khi demo.

### 3.6. Thông báo và nhắc hạn

- Thông báo khi người dùng được giao nhiệm vụ mới.
- Thông báo khi thời hạn nhiệm vụ sắp đến.
- Thông báo khi nhiệm vụ thay đổi trạng thái quan trọng.
- Nhắc các nhiệm vụ đã quá hạn.
- Hiển thị thông báo trong giao diện người dùng.

**Đề xuất:** Dùng Amazon EventBridge Scheduler để kích hoạt tác vụ nhắc hạn, AWS Lambda để xử lý và Amazon SNS hoặc Amazon SES để gửi email.

Thông báo trong ứng dụng có thể được triển khai bằng dữ liệu lưu trữ và truy vấn định kỳ. Gửi email là chức năng bổ sung nếu nhóm còn thời gian.

### 3.7. Dashboard và báo cáo tiến độ

Dashboard cung cấp các thông tin:

- Tổng số dự án đang tham gia.
- Tổng số nhiệm vụ được giao.
- Số nhiệm vụ chưa thực hiện, đang thực hiện và đã hoàn thành.
- Danh sách nhiệm vụ sắp đến hạn.
- Danh sách nhiệm vụ quá hạn.
- Tỷ lệ hoàn thành của từng dự án.
- Tiến độ nhiệm vụ của các thành viên trong dự án.
- Biểu đồ thống kê nhiệm vụ theo trạng thái.

Các số liệu phải được tính dựa trên dữ liệu thực tế của hệ thống, đồng thời giới hạn theo quyền truy cập của người dùng.

### 3.8. Các chức năng có thể mở rộng

- Bảng Kanban để kéo thả nhiệm vụ giữa các trạng thái.
- Lịch hiển thị nhiệm vụ theo ngày, tuần và tháng.
- Bình luận dưới từng nhiệm vụ.
- Đính kèm nhiều tệp cho một nhiệm vụ.
- Lịch sử hoạt động của dự án.
- Xuất báo cáo tiến độ thành CSV hoặc PDF.
- Phân tích khối lượng công việc của từng thành viên.

Các chức năng này không cần đưa vào MVP nếu làm tăng đáng kể độ phức tạp.

## 4. Kịch bản sử dụng minh họa

Giả sử một nhóm gồm bốn sinh viên thực hiện đồ án môn Điện toán đám mây.

1. Một sinh viên tạo tài khoản và đăng nhập vào StudyFlow.
2. Sinh viên này tạo dự án “Xây dựng website quản lý thư viện”.
3. Người tạo dự án trở thành trưởng nhóm và mời ba thành viên còn lại tham gia.
4. Trưởng nhóm tạo các nhiệm vụ như thiết kế giao diện, xây dựng API, thiết kế cơ sở dữ liệu và viết báo cáo.
5. Mỗi nhiệm vụ được gán cho một thành viên, có mô tả, mức độ ưu tiên và thời hạn hoàn thành.
6. Các thành viên đăng nhập để xem nhiệm vụ của mình và cập nhật trạng thái từ `TODO` sang `IN_PROGRESS`, sau đó sang `DONE`.
7. Khi nhiệm vụ sắp đến hạn, hệ thống phát hiện thời hạn phù hợp và tạo thông báo hoặc gửi email theo cấu hình.
8. Trưởng nhóm mở dashboard để xem số lượng nhiệm vụ đã hoàn thành, nhiệm vụ còn tồn đọng và tiến độ của từng thành viên.
9. Các thành viên tải báo cáo, sơ đồ thiết kế hoặc tài liệu cần thiết lên hệ thống để những người có quyền truy cập.
10. Khi toàn bộ nhiệm vụ chính đã hoàn thành, trưởng nhóm đánh dấu dự án hoàn thành và kiểm tra báo cáo tổng hợp.

**Kết quả mong đợi:** Nhóm có thể quản lý công việc trên một nền tảng thống nhất, giảm việc theo dõi thủ công và quan sát được dữ liệu được lưu trữ, xử lý trên AWS.

## 5. Các dịch vụ AWS dự kiến sử dụng

Nhóm có thể sử dụng các dịch vụ sau. Đây là kiến trúc tham khảo, chưa phải cấu hình triển khai chính thức.

### 5.1. Amazon Cognito

Vai trò:

- Đăng ký và đăng nhập người dùng.
- Quản lý danh tính và phiên xác thực.
- Cung cấp token để frontend gọi backend.
- Hỗ trợ xác thực cho các API được bảo vệ.

Cần phân biệt xác thực người dùng với phân quyền nghiệp vụ. Việc một người đăng nhập thành công không đồng nghĩa người đó được phép sửa mọi dự án.

### 5.2. Amazon API Gateway

Vai trò:

- Cung cấp REST API cho frontend.
- Tiếp nhận các yêu cầu tạo, sửa, xóa và đọc dữ liệu.
- Kết nối yêu cầu đến AWS Lambda.
- Tích hợp cơ chế xác thực phù hợp.

Ví dụ: tạo dự án, lấy danh sách nhiệm vụ, cập nhật trạng thái và tải lên tài liệu thông qua các endpoint được bảo vệ.

### 5.3. AWS Lambda

Vai trò:

- Xử lý nghiệp vụ quản lý dự án và nhiệm vụ.
- Kiểm tra dữ liệu đầu vào.
- Kiểm tra quyền của người dùng đối với dự án.
- Đọc và ghi dữ liệu vào DynamoDB.
- Tạo thông báo khi có sự kiện phù hợp.
- Xử lý các tác vụ nhắc hạn theo lịch.

Lambda cho phép triển khai backend theo mô hình serverless mà không cần tự quản lý máy chủ chạy liên tục.

### 5.4. Amazon DynamoDB

Vai trò:

- Lưu thông tin người dùng phục vụ nghiệp vụ ứng dụng.
- Lưu dự án và thành viên.
- Lưu nhiệm vụ, trạng thái và thời hạn.
- Lưu thông báo và lịch sử hoạt động nếu được triển khai.
- Truy vấn dữ liệu phục vụ dashboard.

Nhóm cần thiết kế khóa chính, khóa sắp xếp và các chỉ mục dựa trên những truy vấn thực tế của ứng dụng.

### 5.5. Amazon S3

Vai trò:

- Lưu trữ tệp đính kèm của dự án.
- Lưu trữ tài liệu báo cáo và hình ảnh.
- Hỗ trợ tải lên và tải xuống tệp.
- Tách dữ liệu tệp khỏi dữ liệu nghiệp vụ trong DynamoDB.

Nên sử dụng URL ký trước (presigned URL) khi phù hợp để người dùng được cấp quyền tải tệp trong một khoảng thời gian giới hạn.

### 5.6. Amazon EventBridge Scheduler

Vai trò:

- Kích hoạt tác vụ nhắc hạn theo lịch.
- Gọi Lambda để kiểm tra nhiệm vụ sắp đến hạn hoặc quá hạn.
- Hỗ trợ thực hiện các công việc nền mà không cần người dùng mở giao diện.

Với MVP, nhóm có thể dùng một lịch chạy chung và truy vấn các nhiệm vụ cần nhắc hạn thay vì tạo một lịch riêng cho từng nhiệm vụ.

### 5.7. Amazon SNS hoặc Amazon SES

Vai trò dự kiến:

- Gửi thông báo email cho người dùng khi có sự kiện cần chú ý.
- Nhắc nhiệm vụ sắp đến hạn hoặc quá hạn.
- Thông báo khi có nhiệm vụ mới được giao.

SNS phù hợp với các luồng thông báo đơn giản; SES phù hợp hơn khi cần gửi email ứng dụng có nội dung được kiểm soát. Nhóm nên chọn một phương án phù hợp thay vì bắt buộc triển khai cả hai.

### 5.8. Amazon CloudWatch

Vai trò:

- Thu thập log của Lambda.
- Theo dõi lỗi và thời gian xử lý.
- Quan sát số lần gọi và tình trạng hoạt động của backend.
- Hỗ trợ kiểm tra lỗi trong quá trình demo.

### 5.9. AWS IAM

Vai trò:

- Cấp quyền truy cập giữa các dịch vụ AWS.
- Giới hạn Lambda chỉ được truy cập những bảng DynamoDB, bucket S3 hoặc dịch vụ cần thiết.
- Áp dụng nguyên tắc quyền tối thiểu.
- Hạn chế sử dụng quyền quản trị rộng trong môi trường demo.

### 5.10. Dịch vụ triển khai frontend

Có thể cân nhắc:

- AWS Amplify Hosting để triển khai frontend.
- Hoặc Amazon S3 kết hợp Amazon CloudFront nếu nhóm chọn phương án lưu trữ website tĩnh.

Việc lựa chọn phụ thuộc vào framework frontend, cấu hình triển khai và ngân sách của nhóm.

## 6. Kiến trúc tổng thể của hệ thống

### 6.1. Luồng xử lý chính

Sinh viên sử dụng trình duyệt để truy cập giao diện StudyFlow. Frontend thực hiện xác thực với Amazon Cognito, sau đó gửi yêu cầu đến API Gateway kèm thông tin xác thực.

API Gateway chuyển yêu cầu đến Lambda. Lambda kiểm tra dữ liệu, xác định danh tính người dùng, kiểm tra quyền truy cập và thực hiện nghiệp vụ. Dữ liệu dự án, nhiệm vụ và thông báo được lưu trong DynamoDB; tài liệu được lưu trong S3.

Đối với tác vụ nhắc hạn, EventBridge Scheduler kích hoạt Lambda theo lịch. Lambda truy vấn các nhiệm vụ cần xử lý và tạo thông báo hoặc gửi email qua dịch vụ thông báo đã lựa chọn.

CloudWatch thu thập log và các chỉ số cần thiết để nhóm kiểm tra hoạt động của hệ thống.

### 6.2. Sơ đồ kiến trúc logic

```text
                 SINH VIÊN
                     |
                  Trình duyệt
                     |
             Frontend StudyFlow
                     |
          +----------+----------+
          |                     |
   Amazon Cognito         Amazon S3
   Xác thực tài khoản     Tài liệu dự án
          |
          +------ Frontend nhận token
                     |
               Amazon API Gateway
                     |
                 AWS Lambda
                     |
          +----------+-----------+
          |          |           |
      DynamoDB      S3       Dịch vụ thông báo
      Dữ liệu    Tài liệu    SNS hoặc SES
          ^
          |
     AWS Lambda
          ^
          |
 EventBridge Scheduler
    Nhắc hạn định kỳ

     Amazon CloudWatch
       Theo dõi và log

        AWS IAM
   Quản lý quyền dịch vụ
```

Sơ đồ trên mô tả các thành phần chính ở mức logic. Khi triển khai, nhóm cần xác định chính xác cách Cognito tích hợp với API Gateway, cách Lambda truy cập dữ liệu và cách frontend nhận quyền tải tệp.

### 6.3. Hai luồng nghiệp vụ cần chứng minh

**Luồng 1 — Quản lý nhiệm vụ:**

Sinh viên đăng nhập → tạo dự án → thêm thành viên → tạo nhiệm vụ → phân công → cập nhật trạng thái → dashboard cập nhật tiến độ.

**Luồng 2 — Nhắc hạn tự động:**

EventBridge Scheduler → Lambda → truy vấn nhiệm vụ đến hạn → tạo thông báo → gửi email nếu được cấu hình → ghi log CloudWatch.

Hai luồng này thể hiện được cả nghiệp vụ ứng dụng lẫn việc sử dụng các dịch vụ điện toán đám mây.

## 7. Mô hình dữ liệu khái niệm

Dưới đây là các nhóm dữ liệu dự kiến. Đây chưa phải schema DynamoDB chính thức.

### 7.1. User

Lưu thông tin người dùng của ứng dụng.

Các trường tham khảo:

- `userId`: Mã người dùng nội bộ.
- `cognitoSub`: Định danh người dùng từ Cognito.
- `fullName`: Họ tên.
- `email`: Email.
- `avatarUrl`: Đường dẫn ảnh đại diện nếu có.
- `createdAt`: Thời điểm tạo tài khoản trong ứng dụng.
- `updatedAt`: Thời điểm cập nhật gần nhất.

Mục đích: liên kết tài khoản đã xác thực với dữ liệu nghiệp vụ của hệ thống.

### 7.2. Project

Lưu thông tin dự án.

Các trường tham khảo:

- `projectId`: Mã dự án.
- `name`: Tên dự án.
- `description`: Mô tả.
- `ownerId`: Người tạo hoặc chủ sở hữu dự án.
- `startDate`: Ngày bắt đầu.
- `dueDate`: Thời hạn dự kiến.
- `status`: Trạng thái dự án.
- `createdAt`: Thời điểm tạo.
- `updatedAt`: Thời điểm cập nhật.

Mục đích: quản lý thông tin chung của dự án và phục vụ dashboard.

### 7.3. ProjectMember

Lưu mối quan hệ giữa người dùng và dự án.

Các trường tham khảo:

- `projectId`: Mã dự án.
- `userId`: Mã người dùng.
- `role`: Vai trò trong dự án.
- `joinedAt`: Thời điểm tham gia.
- `membershipStatus`: Trạng thái thành viên nếu cần.

Mục đích: xác định ai là thành viên của dự án và mỗi người có quyền gì.

### 7.4. Task

Lưu thông tin nhiệm vụ.

Các trường tham khảo:

- `taskId`: Mã nhiệm vụ.
- `projectId`: Mã dự án, có thể để trống đối với nhiệm vụ cá nhân.
- `title`: Tên nhiệm vụ.
- `description`: Mô tả.
- `assigneeId`: Người được giao nhiệm vụ.
- `createdBy`: Người tạo nhiệm vụ.
- `status`: Trạng thái công việc.
- `priority`: Mức độ ưu tiên.
- `dueDate`: Thời hạn hoàn thành.
- `createdAt`: Thời điểm tạo.
- `updatedAt`: Thời điểm cập nhật.
- `completedAt`: Thời điểm hoàn thành, nếu có.

Mục đích: quản lý vòng đời nhiệm vụ và hỗ trợ truy vấn theo dự án, người phụ trách, trạng thái và thời hạn.

### 7.5. Attachment

Lưu thông tin tài liệu liên quan đến dự án hoặc nhiệm vụ.

Các trường tham khảo:

- `attachmentId`: Mã tệp đính kèm.
- `projectId`: Mã dự án.
- `taskId`: Mã nhiệm vụ nếu tệp gắn với một nhiệm vụ.
- `uploadedBy`: Người tải lên.
- `fileName`: Tên tệp.
- `s3Key`: Khóa đối tượng trong S3.
- `contentType`: Loại nội dung.
- `fileSize`: Dung lượng tệp.
- `createdAt`: Thời điểm tải lên.

Mục đích: lưu metadata để ứng dụng quản lý tài liệu mà không phải lưu toàn bộ nội dung tệp trong DynamoDB.

### 7.6. Notification

Lưu thông báo dành cho người dùng.

Các trường tham khảo:

- `notificationId`: Mã thông báo.
- `userId`: Người nhận.
- `projectId`: Dự án liên quan nếu có.
- `taskId`: Nhiệm vụ liên quan nếu có.
- `type`: Loại thông báo.
- `message`: Nội dung.
- `isRead`: Trạng thái đã đọc.
- `createdAt`: Thời điểm tạo.
- `sentAt`: Thời điểm gửi email nếu áp dụng.

Mục đích: hiển thị thông báo và theo dõi trạng thái đọc.

### 7.7. ActivityLog

Có thể bổ sung để lưu lịch sử thao tác quan trọng.

Các trường tham khảo:

- `activityId`: Mã hoạt động.
- `projectId`: Mã dự án.
- `actorId`: Người thực hiện.
- `action`: Loại thao tác.
- `entityType`: Loại đối tượng bị thay đổi.
- `entityId`: Mã đối tượng.
- `createdAt`: Thời điểm thao tác.

Mục đích: giúp trưởng nhóm xem lại những thay đổi quan trọng và hỗ trợ điều tra khi xảy ra lỗi.

### 7.8. Các quyết định cần thống nhất về DynamoDB

Nhóm cần xác định:

- Dùng một bảng DynamoDB với thiết kế single-table hay nhiều bảng theo từng nhóm dữ liệu.
- Cách truy vấn danh sách dự án theo người dùng.
- Cách truy vấn nhiệm vụ theo người phụ trách và thời hạn.
- Cách truy vấn nhiệm vụ theo dự án và trạng thái.
- Cách lấy thông báo chưa đọc.
- Cách tạo chỉ mục phụ (GSI) khi cần.
- Quy tắc phân trang, thời gian lưu dữ liệu và xử lý dữ liệu bị xóa.

Không nên chọn cấu trúc bảng chỉ dựa vào tên thực thể. Thiết kế phải đáp ứng được các truy vấn mà frontend và dashboard thực sự cần.

## 8. API cho hệ thống

Các endpoint sau là đề xuất minh họa cho REST API được triển khai thông qua API Gateway và Lambda.

### 8.1. Tài khoản và thông tin cá nhân

- `GET /me`: Lấy thông tin người dùng đang đăng nhập.
- `PATCH /me`: Cập nhật thông tin cá nhân.

Đăng ký, đăng nhập và xử lý phiên đăng nhập được giao cho Cognito hoặc cơ chế xác thực đã lựa chọn.

### 8.2. Quản lý dự án

- `POST /projects`: Tạo dự án.
- `GET /projects`: Lấy danh sách dự án mà người dùng được phép xem.
- `GET /projects/{projectId}`: Xem chi tiết dự án.
- `PATCH /projects/{projectId}`: Cập nhật thông tin dự án.
- `DELETE /projects/{projectId}`: Xóa dự án nếu chính sách cho phép.
- `GET /projects/{projectId}/members`: Xem danh sách thành viên.
- `POST /projects/{projectId}/members`: Thêm hoặc mời thành viên.
- `DELETE /projects/{projectId}/members/{userId}`: Xóa thành viên nếu được phép.

### 8.3. Quản lý nhiệm vụ

- `POST /tasks`: Tạo nhiệm vụ.
- `GET /tasks`: Lấy danh sách nhiệm vụ theo bộ lọc.
- `GET /tasks/{taskId}`: Xem chi tiết nhiệm vụ.
- `PATCH /tasks/{taskId}`: Cập nhật nhiệm vụ.
- `DELETE /tasks/{taskId}`: Xóa nhiệm vụ nếu được phép.
- `PATCH /tasks/{taskId}/status`: Cập nhật trạng thái.
- `GET /projects/{projectId}/tasks`: Lấy nhiệm vụ trong một dự án.

### 8.4. Quản lý tài liệu

- `POST /attachments/upload-url`: Yêu cầu URL ký trước để tải tệp lên.
- `POST /attachments`: Ghi nhận metadata của tệp sau khi tải lên.
- `GET /attachments/{attachmentId}/download-url`: Yêu cầu URL tải xuống.
- `DELETE /attachments/{attachmentId}`: Xóa tệp theo quyền được cấp.

### 8.5. Dashboard và thông báo

- `GET /dashboard/summary`: Lấy số liệu tổng quan.
- `GET /dashboard/projects/{projectId}`: Lấy tiến độ của dự án.
- `GET /notifications`: Lấy danh sách thông báo.
- `PATCH /notifications/{notificationId}`: Đánh dấu thông báo đã đọc.

### 8.6. Các yêu cầu đối với API

- Kiểm tra dữ liệu đầu vào và trả về lỗi rõ ràng.
- Sử dụng mã HTTP phù hợp.
- Kiểm tra quyền truy cập đối với từng dự án và nhiệm vụ.
- Không cho phép người dùng đọc dữ liệu của dự án mà họ không tham gia.
- Có phân trang đối với danh sách dài.
- Không trả về thông tin nội bộ, token hoặc thông tin nhạy cảm trong response.
- Không cho phép client tự quyết định quyền sở hữu bằng cách gửi `userId` tùy ý.

Ví dụ, khi cập nhật nhiệm vụ, backend phải xác định người dùng từ token đã xác thực, sau đó kiểm tra người dùng có quyền sửa nhiệm vụ đó hay không.

## 9. Giao diện và dashboard dự kiến

### 9.1. Trang đăng nhập

- Form đăng nhập.
- Chức năng đăng ký nếu nhóm triển khai luồng đăng ký.
- Thông báo lỗi khi xác thực không thành công.
- Chuyển hướng đến dashboard sau khi đăng nhập.

### 9.2. Dashboard cá nhân

- Tổng số dự án đang tham gia.
- Tổng số nhiệm vụ được giao.
- Số nhiệm vụ đã hoàn thành.
- Số nhiệm vụ đang thực hiện.
- Số nhiệm vụ quá hạn.
- Danh sách nhiệm vụ sắp đến hạn.
- Biểu đồ phân bố nhiệm vụ theo trạng thái.

### 9.3. Trang quản lý dự án

- Danh sách dự án.
- Tạo dự án mới.
- Tìm kiếm và lọc dự án.
- Hiển thị trạng thái và thời hạn.
- Mở trang chi tiết dự án.

### 9.4. Trang chi tiết dự án

- Thông tin chung.
- Danh sách thành viên.
- Danh sách nhiệm vụ.
- Chức năng thêm và phân công nhiệm vụ.
- Hiển thị tiến độ dự án.
- Danh sách tài liệu liên quan.
- Các thao tác chỉ dành cho trưởng nhóm hoặc người có quyền.

### 9.5. Trang quản lý nhiệm vụ

- Danh sách nhiệm vụ.
- Bộ lọc theo trạng thái, ưu tiên và thời hạn.
- Chi tiết nhiệm vụ.
- Chức năng cập nhật trạng thái.
- Hiển thị người phụ trách và thời hạn.

Giao diện cần có trạng thái tải dữ liệu, trạng thái danh sách rỗng và thông báo lỗi để người dùng hiểu rõ tình trạng của hệ thống.

## 10. Bảo mật, độ tin cậy và chi phí

### 10.1. Bảo mật

- **Xác thực:** Sử dụng Cognito hoặc cơ chế xác thực được lựa chọn để xác minh người dùng.
- **Phân quyền:** Kiểm tra vai trò của người dùng trong từng dự án ở backend.
- **IAM least privilege:** Mỗi Lambda chỉ có các quyền cần thiết.
- **Bảo vệ dữ liệu:** Không công khai bucket S3 chứa tài liệu riêng tư.
- **Tải tệp an toàn:** Giới hạn kích thước, loại tệp và thời hạn sử dụng URL ký trước.
- **Bảo vệ API:** Kiểm tra đầu vào, giới hạn truy cập khi phù hợp và tránh để lộ dữ liệu của người dùng khác.
- **Quản lý bí mật:** Không đưa access key, secret key hoặc thông tin xác thực vào mã nguồn frontend.
- **HTTPS:** Sử dụng kết nối bảo mật khi triển khai hệ thống cho người dùng.
- **Ghi log:** Không ghi token, mật khẩu hoặc thông tin nhạy cảm vào CloudWatch.

Cần đặc biệt kiểm tra các tình huống người dùng cố truy cập nhiệm vụ bằng cách thay đổi `taskId` hoặc `projectId` trên request.

### 10.2. Độ tin cậy

- Kiểm tra và xử lý lỗi từ API, DynamoDB và S3.
- Sử dụng cơ chế phân trang để tránh truy vấn quá nhiều dữ liệu.
- Thiết kế tác vụ nhắc hạn có khả năng chạy lại mà không tạo quá nhiều thông báo trùng.
- Kiểm tra các trường hợp nhiệm vụ bị chỉnh sửa hoặc xóa trong lúc tác vụ nhắc hạn đang chạy.
- Xử lý trường hợp gửi email thất bại.
- Lưu thời gian theo một quy ước thống nhất, ưu tiên UTC trong dữ liệu backend và hiển thị theo múi giờ phù hợp ở giao diện.
- Kiểm tra log và metric trong quá trình thử nghiệm.

### 10.3. Chi phí

Các thành phần cần xem xét khi ước tính chi phí gồm:

- API Gateway: số lượng yêu cầu API.
- Lambda: số lần gọi, thời gian thực thi và cấu hình bộ nhớ.
- DynamoDB: phương thức tính dung lượng đọc/ghi, lưu trữ và số lượng truy vấn.
- S3: dung lượng tệp, yêu cầu tải lên/tải xuống và truyền dữ liệu.
- Cognito: mức sử dụng và các điều kiện tính phí hiện hành.
- EventBridge Scheduler: số lượng lịch và số lần kích hoạt.
- SNS hoặc SES: số lượng thông báo và email.
- CloudWatch: lượng log, thời gian lưu trữ và metric.
- Dịch vụ hosting frontend nếu có.

Không nên đưa ra một con số chi phí cố định khi chưa xác định region, lưu lượng sử dụng, cấu hình và bảng giá hiện hành.

Nhóm cần thống nhất AWS account hoặc sandbox được phép sử dụng, giới hạn ngân sách, người chịu trách nhiệm và quy trình xóa tài nguyên sau demo. Cần lưu ý rằng cảnh báo ngân sách không nhất thiết tự động ngừng các dịch vụ đang phát sinh chi phí.

## 11. Kế hoạch triển khai đề xuất

### Giai đoạn 1 — Phân tích yêu cầu

- Xác định người dùng mục tiêu.
- Liệt kê các chức năng bắt buộc.
- Xác định các vai trò và quyền truy cập.
- Vẽ sơ đồ Use Case.
- Xác định các luồng nghiệp vụ chính.
- Chốt phạm vi MVP với giảng viên.

**Kết quả:** Tài liệu yêu cầu chức năng, phi chức năng và phạm vi đồ án.

### Giai đoạn 2 — Thiết kế hệ thống

- Thiết kế kiến trúc tổng thể AWS.
- Thiết kế sơ đồ cơ sở dữ liệu hoặc sơ đồ thực thể.
- Xác định cấu trúc DynamoDB.
- Thiết kế REST API.
- Thiết kế giao diện chính.
- Xác định chính sách xác thực và phân quyền.

**Kết quả:** Sơ đồ kiến trúc, mô hình dữ liệu, danh sách API và bản thiết kế giao diện.

### Giai đoạn 3 — Xây dựng frontend

- Xây dựng giao diện đăng nhập.
- Xây dựng dashboard.
- Xây dựng trang quản lý dự án.
- Xây dựng trang quản lý nhiệm vụ.
- Xây dựng trang thành viên và tài liệu nếu thuộc MVP.
- Kết nối frontend với API.

Framework frontend cần được thống nhất trước khi triển khai.

### Giai đoạn 4 — Xây dựng backend trên AWS

- Thiết lập Cognito.
- Tạo API Gateway và Lambda.
- Thiết kế DynamoDB.
- Xây dựng nghiệp vụ quản lý dự án và nhiệm vụ.
- Tích hợp S3 cho tài liệu nếu nằm trong phạm vi.
- Cấu hình IAM.
- Thiết lập CloudWatch logs.

**Kết quả:** Backend hoạt động với các API cơ bản và dữ liệu được lưu trữ trên AWS.

### Giai đoạn 5 — Tích hợp thông báo

- Xác định các trường hợp cần thông báo.
- Cấu hình EventBridge Scheduler.
- Xây dựng Lambda xử lý nhắc hạn.
- Tích hợp SNS hoặc SES nếu nhóm chọn gửi email.
- Kiểm tra lịch chạy và tránh tạo thông báo trùng.

Nếu thời gian hạn chế, nhóm có thể hoàn thành chức năng quản lý nhiệm vụ trước, sau đó bổ sung nhắc hạn tự động.

### Giai đoạn 6 — Kiểm thử và hoàn thiện

- Kiểm thử chức năng đăng nhập.
- Kiểm thử tạo và chỉnh sửa dự án.
- Kiểm thử phân công và cập nhật nhiệm vụ.
- Kiểm thử phân quyền.
- Kiểm thử tải lên và tải xuống tài liệu nếu có.
- Kiểm thử nhắc hạn.
- Kiểm tra lỗi và log CloudWatch.
- Ước tính chi phí và kiểm tra tài nguyên AWS.

### Giai đoạn 7 — Triển khai và demo

- Triển khai frontend.
- Cấu hình API và môi trường production/demo.
- Chuẩn bị tài khoản demo và dữ liệu mẫu.
- Chạy thử toàn bộ kịch bản.
- Chụp ảnh hoặc ghi lại bằng chứng triển khai.
- Chuẩn bị báo cáo, slide và sơ đồ kiến trúc.
- Dọn dẹp tài nguyên thử nghiệm sau khi được phê duyệt.

## 12. Kịch bản demo dự kiến

### Bước 1 — Đăng nhập hệ thống

- Đăng nhập bằng tài khoản sinh viên đã chuẩn bị.
- Hiển thị dashboard cá nhân.
- Chứng minh hệ thống nhận diện người dùng.

**Bằng chứng:** Giao diện đăng nhập thành công và dữ liệu cá nhân tương ứng.

### Bước 2 — Tạo dự án

- Tạo dự án “Đồ án môn Điện toán đám mây”.
- Nhập mô tả và thời hạn dự kiến.
- Hiển thị dự án trong danh sách.

**Bằng chứng:** Dự án xuất hiện trên dashboard và dữ liệu được lưu trong DynamoDB.

### Bước 3 — Thêm thành viên

- Mời một hoặc nhiều tài khoản demo tham gia dự án.
- Hiển thị danh sách thành viên.
- Kiểm tra vai trò trưởng nhóm và thành viên.

**Bằng chứng:** Thành viên được ghi nhận và quyền truy cập được kiểm tra.

### Bước 4 — Tạo và phân công nhiệm vụ

- Tạo các nhiệm vụ thiết kế giao diện, xây dựng API và viết báo cáo.
- Đặt thời hạn và mức độ ưu tiên.
- Phân công từng nhiệm vụ cho thành viên.

**Bằng chứng:** Danh sách nhiệm vụ và thông tin người phụ trách hiển thị chính xác.

### Bước 5 — Cập nhật tiến độ

- Một thành viên chuyển nhiệm vụ từ `TODO` sang `IN_PROGRESS`.
- Sau khi hoàn thành, cập nhật sang `DONE`.
- Trưởng nhóm mở dashboard để xem thống kê mới.

**Bằng chứng:** Trạng thái nhiệm vụ và tỷ lệ hoàn thành dự án thay đổi theo dữ liệu thực tế.

### Bước 6 — Kiểm tra chức năng nhắc hạn

- Chuẩn bị một nhiệm vụ có thời hạn phù hợp với kịch bản demo.
- Kích hoạt tác vụ theo lịch hoặc sử dụng thời gian thử nghiệm đã cấu hình.
- Kiểm tra thông báo được tạo hoặc email được gửi.

**Bằng chứng:** Log của Lambda, bản ghi thông báo và email nếu có.

### Bước 7 — Kiểm tra tài liệu

Nếu chức năng quản lý tài liệu nằm trong MVP:

- Tải một tệp báo cáo lên dự án.
- Kiểm tra metadata trong ứng dụng.
- Tải xuống bằng tài khoản được cấp quyền.
- Kiểm tra tài khoản không có quyền không thể truy cập tài liệu riêng tư.

**Bằng chứng:** Tệp trong S3, metadata tương ứng và kết quả kiểm tra phân quyền.

### Bước 8 — Kiểm tra hoạt động AWS

- Mở CloudWatch để xem log.
- Trình bày luồng API Gateway → Lambda → DynamoDB.
- Trình bày EventBridge Scheduler nếu đã triển khai.
- Kiểm tra cấu hình IAM.
- Trình bày ước tính chi phí và kế hoạch dọn dẹp tài nguyên.

**Bằng chứng:** Tài nguyên AWS thực tế, log thực thi và dữ liệu được lưu trữ.

## 13. Điểm nổi bật và giới hạn của đề tài

### 13.1. Điểm nổi bật

- Giải quyết nhu cầu thực tế của sinh viên khi thực hiện bài tập và đồ án nhóm.
- Có nhiều nghiệp vụ rõ ràng để phân tích và triển khai.
- Thể hiện kiến thức Cloud Computing thông qua serverless, API, lưu trữ dữ liệu, quản lý danh tính và tự động hóa.
- Tách biệt frontend, backend và dữ liệu.
- Có thể kiểm chứng bằng dữ liệu thực tế thay vì chỉ trình bày giao diện.
- Có khả năng mở rộng chức năng theo nhu cầu.
- Phù hợp để thực hành bảo mật, quản lý quyền, giám sát và tối ưu chi phí trên AWS.

### 13.2. Những thách thức

- Thiết kế DynamoDB phù hợp với các truy vấn nghiệp vụ.
- Đảm bảo phân quyền đúng giữa trưởng nhóm và thành viên.
- Xử lý nhất quán trạng thái nhiệm vụ và tiến độ dự án.
- Triển khai nhắc hạn mà không tạo thông báo trùng.
- Bảo vệ tài liệu được lưu trữ trên S3.
- Kiểm soát chi phí dịch vụ trong môi trường sinh viên.
- Hoàn thiện cả frontend và backend trong thời gian có hạn.

### 13.3. Định vị đề tài

StudyFlow là một ứng dụng quản lý công việc học tập được xây dựng trên AWS, tập trung vào việc kết hợp quản lý dự án, phân công nhiệm vụ, theo dõi tiến độ và thông báo trên một nền tảng thống nhất.

Đồ án không cần tuyên bố tạo ra một công nghệ quản lý dự án mới. Giá trị của đề tài nằm ở việc thiết kế, tích hợp và triển khai một hệ thống hoàn chỉnh, có nghiệp vụ thực tế và có bằng chứng hoạt động trên nền tảng đám mây.

## 14. Phạm vi phiên bản tối thiểu (MVP) đề xuất

Để hạn chế rủi ro quá tải, nhóm nên ưu tiên một phiên bản có thể triển khai và demo được trước.

### 14.1. Chức năng bắt buộc của MVP

1. Giao diện đăng nhập và xác thực người dùng.
2. Tạo và xem danh sách dự án.
3. Thêm thành viên vào dự án.
4. Tạo, chỉnh sửa và xem nhiệm vụ.
5. Phân công nhiệm vụ cho thành viên.
6. Cập nhật trạng thái nhiệm vụ.
7. Dashboard thống kê nhiệm vụ và tiến độ.
8. Backend triển khai bằng API Gateway và Lambda.
9. Dữ liệu dự án và nhiệm vụ lưu trong DynamoDB.
10. Sử dụng IAM để giới hạn quyền truy cập và CloudWatch để theo dõi log.

### 14.2. Chức năng nên triển khai sau MVP

- Lưu trữ tài liệu trên S3.
- Nhắc hạn tự động bằng EventBridge Scheduler.
- Gửi email qua SNS hoặc SES.
- Lịch sử hoạt động dự án.
- Bình luận và bảng Kanban.
- Báo cáo nâng cao và xuất dữ liệu.
- Phân tích khối lượng công việc.
- Các chức năng tối ưu hiệu năng hoặc mở rộng quy mô.

Thứ tự ưu tiên có thể điều chỉnh tùy yêu cầu giảng viên. Nếu yêu cầu môn học nhấn mạnh khả năng sử dụng nhiều dịch vụ AWS, nhóm nên lựa chọn thêm một hoặc hai luồng Cloud có giá trị rõ ràng thay vì bổ sung nhiều chức năng giao diện nhưng không làm rõ vai trò của AWS.

## 15. Tiêu chí thành công cho bản demo

Bản demo được xem là đạt yêu cầu cơ bản khi:

- Người dùng đăng nhập được bằng tài khoản hợp lệ.
- Tạo được một dự án mới.
- Thêm được thành viên vào dự án.
- Tạo và phân công được nhiệm vụ.
- Cập nhật được trạng thái nhiệm vụ.
- Dashboard phản ánh chính xác số lượng và tiến độ công việc.
- Dữ liệu được lưu và truy vấn từ DynamoDB.
- Người không có quyền không thể đọc hoặc sửa dữ liệu dự án trái phép.
- Log CloudWatch thể hiện được các lần thực thi backend.
- Các dịch vụ AWS được cấu hình với quyền phù hợp.
- Nếu triển khai nhắc hạn, hệ thống có thể chứng minh được luồng kích hoạt tác vụ và tạo thông báo.
- Nếu triển khai tài liệu, tệp được lưu trong S3 và kiểm soát truy cập đúng.
- Nhóm trình bày được kiến trúc, luồng dữ liệu, cách kiểm thử và chi phí dự kiến.
- Có kế hoạch dọn dẹp tài nguyên AWS sau khi hoàn thành demo.

## 16. Những quyết định cần nhóm và giảng viên thống nhất

1. Đồ án bắt buộc phải sử dụng những dịch vụ AWS nào?
2. Số lượng chức năng tối thiểu được yêu cầu là gì?
3. Có cần đăng ký tài khoản sinh viên hay chỉ sử dụng tài khoản được tạo sẵn?
4. Thành viên được tham gia dự án bằng email, mã mời hay cơ chế khác?
5. Trưởng nhóm có những quyền gì và thành viên được phép sửa nhiệm vụ đến mức nào?
6. Có cần quản lý nhiệm vụ cá nhân ngoài dự án nhóm không?
7. Có bắt buộc chức năng tải lên tài liệu không?
8. Có bắt buộc gửi email nhắc hạn hay chỉ cần thông báo trong ứng dụng?
9. Nên chọn DynamoDB hay một hệ quản trị cơ sở dữ liệu khác nếu giảng viên yêu cầu quan hệ dữ liệu rõ ràng?
10. Frontend sử dụng framework nào và được triển khai ở đâu?
11. Có cần phân trang, tìm kiếm nâng cao và lịch sử thao tác không?
12. Có yêu cầu về hiệu năng, số lượng người dùng hoặc kiểm thử tải không?
13. AWS account, region, ngân sách và giới hạn tài nguyên được cấp là gì?
14. Yêu cầu báo cáo, slide, video demo và thời lượng thuyết trình ra sao?
15. Những bằng chứng nào cần có để chứng minh hệ thống thực sự chạy trên AWS?

## 17. Tổng hợp định hướng triển khai

### 17.1. Định hướng chính

- Xây dựng StudyFlow làm nền tảng quản lý nhiệm vụ và dự án cho sinh viên.
- Sử dụng Cognito để xác thực người dùng.
- Sử dụng API Gateway và Lambda để xây dựng backend serverless.
- Sử dụng DynamoDB để lưu thông tin dự án, thành viên và nhiệm vụ.
- Sử dụng S3 để lưu tài liệu nếu chức năng này thuộc phạm vi triển khai.
- Sử dụng EventBridge Scheduler kết hợp Lambda để tự động xử lý nhắc hạn.
- Sử dụng SNS hoặc SES nếu cần gửi email.
- Sử dụng IAM để quản lý quyền và CloudWatch để theo dõi hệ thống.
- Bắt đầu bằng MVP, sau đó mở rộng các chức năng dựa trên thời gian và ngân sách.

### 17.2. Nguyên tắc thực hiện

1. Ưu tiên chức năng nghiệp vụ cốt lõi trước.
2. Thiết kế quyền truy cập ngay từ đầu.
3. Chọn dịch vụ AWS theo nhu cầu cụ thể, không sử dụng dịch vụ chỉ để tăng số lượng.
4. Kiểm thử từng thành phần trước khi tích hợp.
5. Chuẩn bị dữ liệu demo có thể tái sử dụng.
6. Ghi lại bằng chứng triển khai và các quyết định thiết kế.
7. Theo dõi ngân sách và dọn dẹp tài nguyên khi không sử dụng.

### 17.3. Kết quả dự kiến

Sau khi hoàn thành, nhóm có một ứng dụng quản lý nhiệm vụ và dự án hoạt động trên nền tảng AWS, hỗ trợ sinh viên tạo dự án, phân công công việc, cập nhật tiến độ và theo dõi kết quả.

Đồng thời, nhóm có thể trình bày một kiến trúc Cloud có đầy đủ luồng xử lý từ frontend đến backend, cơ sở dữ liệu, xác thực, giám sát và các tác vụ tự động nếu được triển khai.

Đây là cơ sở để phát triển báo cáo đồ án, sơ đồ kiến trúc, thiết kế cơ sở dữ liệu, phân công công việc và kế hoạch demo chính thức.
