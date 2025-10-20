---
title: "Bản đề xuất"
date: "2025-10-10"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Tại phần này, bạn cần tóm tắt các nội dung trong workshop mà bạn **dự tính** sẽ làm.

# Travel Journal
## Giải pháp AWS Serverless cho nhật ký du lịch

### 1. Tóm tắt điều hành  
Travel Journal Web ra đời với mong muốn giúp mỗi người lưu giữ hành trình của cuộc đời — không chỉ là những chuyến đi, mà còn là ký ức, cảm xúc và câu chuyện đằng sau từng bức ảnh. Ứng dụng kết nối con người với trải nghiệm, biến mỗi chuyến đi thành một phần trong “bản đồ ký ức” của riêng họ.

Người dùng có thể tải lên hình ảnh, ghi chú địa điểm, và hệ thống tự động nhận diện loại cảnh (biển, núi, thành phố…) nhờ Amazon Rekognition. Dữ liệu hành trình được hiển thị trực quan trên bản đồ thời gian thực bằng Amazon Location Service, mang đến trải nghiệm sinh động và gắn kết.

Nền tảng tận dụng sức mạnh của AWS Serverless Architecture (Lambda, API Gateway, S3, DynamoDB, Cognito), đảm bảo hiệu năng cao, bảo mật mạnh mẽ và khả năng mở rộng linh hoạt với chi phí tối ưu.

### 2. Tuyên bố vấn đề  
*Vấn đề hiện tại*  
Nhiều người yêu du lịch muốn lưu giữ hành trình của mình, nhưng các nền tảng hiện nay chỉ cho phép đăng ảnh hoặc ghi chú rời rạc, thiếu sự kết nối trực quan giữa cảm xúc, hình ảnh và địa điểm thực tế. Việc sắp xếp kỷ niệm trở nên khó khăn, không thể xem lại hành trình trên bản đồ hay thống kê được số điểm đến, thời gian và trải nghiệm theo từng chuyến đi. Bên cạnh đó, các nền tảng lưu trữ đám mây phổ biến lại không cá nhân hóa trải nghiệm cho từng người dùng. 

*Giải pháp*  
Travel Journal Web được xây dựng dưới dạng ứng dụng web, tận dụng kiến trúc AWS Serverless để tối ưu hiệu năng và chi phí. Hệ thống sử dụng Amazon S3 để lưu trữ hình ảnh và ghi chú hành trình, kết hợp Amazon Rekognition nhằm tự động nhận diện nội dung ảnh (biển, núi, thành phố, v.v.). Amazon Location Service được tích hợp để trực quan hóa hành trình trên bản đồ tương tác. Người dùng đăng nhập an toàn qua Amazon Cognito, trong khi AWS Lambda và API Gateway xử lý các yêu cầu lưu, hiển thị và phân tích dữ liệu du lịch theo thời gian thực.
Dữ liệu hành trình được lưu trữ và phân tích bởi Amazon DynamoDB và Amazon OpenSearch, hỗ trợ khả năng tìm kiếm, thống kê và lọc dữ liệu nhanh chóng. Cuối cùng, Amazon CloudFront phân phối nội dung tĩnh như hình ảnh, bản đồ và trang web đến người dùng trên toàn cầu với tốc độ cao và độ trễ thấp. Giao diện web thân thiện giúp người dùng dễ dàng tạo nhật ký du lịch, gắn thẻ cảm xúc, chia sẻ hành trình và xem lại bản đồ kỷ niệm của mình ở bất cứ đâu.

*Lợi ích và hoàn vốn đầu tư (ROI)* 
Giải pháp giúp người dùng dễ dàng lưu trữ và chia sẻ hành trình du lịch, đồng thời tạo nền tảng dữ liệu để mở rộng thành ứng dụng du lịch cộng đồng trong tương lai. Với chi phí chỉ khoảng 14.55 USD/tháng, ứng dụng có thể phục vụ 100–200 người dùng mà không cần máy chủ vật lý. Thời gian hoàn vốn ước tính 6–8 tháng, nhờ tiết kiệm chi phí vận hành, bảo trì và lưu trữ ảnh tập trung.  

### 3. Kiến trúc giải pháp  
Nền tảng áp dụng kiến trúc AWS Serverless và Managed Services để triển khai hệ thống Travel Journal App đảm bảo tính linh hoạt, bảo mật và chi phí tối ưu. Giao diện web tĩnh được phân phối toàn cầu qua Amazon CloudFront, bảo vệ bởi AWS WAF và ánh xạ tên miền thông qua Amazon Route 53. Dữ liệu người dùng và hình ảnh được lưu trữ trong Amazon S3, trong khi AWS Lambda kết hợp với API Gateway xử lý logic phía máy chủ. Amazon Cognito đảm nhiệm xác thực và phân quyền người dùng. Các tác vụ nhận diện hình ảnh được xử lý bằng Amazon Rekognition, dữ liệu vị trí được cung cấp bởi Amazon Location Service. Dữ liệu hành trình, thông tin người dùng và nội dung bài viết được lưu trong Amazon DynamoDB, đồng thời được tìm kiếm nâng cao bằng Amazon OpenSearch Service. Ảnh và tệp phương tiện được lưu trữ trong Amazon S3. Ngoài ra, Amazon SNS được dùng để gửi thông báo tự động cho người dùng và quản trị viên. Toàn bộ hệ thống được giám sát bởi Amazon CloudWatch và AWS X-Ray, đảm bảo hoạt động ổn định, hiệu năng cao và khả năng mở rộng linh hoạt.

![Travel journal Architecture](/images/2-Proposal/proposal.jpg)


*Dịch vụ AWS sử dụng*  
- Amazon Route 53: Quản lý tên miền và định tuyến truy cập toàn cầu.
- Amazon CloudFront: Phân phối nội dung tĩnh và động với độ trễ thấp.
- AWS WAF: Bảo vệ ứng dụng khỏi các mối đe dọa web phổ biến.
- AWS Lambda: Xử lý sự kiện và logic phía máy chủ mà không cần quản lý hạ tầng.
- Amazon API Gateway: Trung gian giữa frontend và backend, tiếp nhận yêu cầu từ người dùng và chuyển đến AWS Lambda.
- Amazon S3: Lưu trữ hình ảnh, dữ liệu người dùng, và nhật ký hoạt động.
- Amazon DynamoDB: Lưu trữ dữ liệu phi quan hệ về hành trình, địa điểm và thông tin bài viết, tối ưu tốc độ truy cập.
- Amazon Cognito: Quản lý xác thực và quyền truy cập người dùng.
- Amazon Rekognition: Phân tích, nhận diện hình ảnh.
- Amazon Location Service: Cung cấp dịch vụ định vị và bản đồ.
- Amazon OpenSearch Service: Cung cấp khả năng tìm kiếm và phân tích dữ liệu hành trình nhanh chóng, linh hoạt.
- Amazon SNS: Gửi thông báo đến người dùng và quản trị viên.
- Amazon CloudWatch: Giám sát hoạt động, log và hiệu năng dịch vụ.
- AWS X-Ray: Theo dõi chi tiết luồng request trong hệ thống serverless. 
- AWS IAM: Quản lý quyền truy cập, cấp vai trò cho Lambda, API Gateway và dịch vụ AWS khác.
- AWS Secrets Manager: Lưu trữ và mã hóa thông tin bí mật
- AWS Certificate Manager: Cấp phát và quản lý chứng chỉ SSL/TLS cho các endpoint bảo mật.
- AWS Config: Theo dõi thay đổi cấu hình và đảm bảo tuân thủ bảo mật trong môi trường AWS


*Thiết kế thành phần*  
- Xác thực người dùng: Amazon Cognito đảm nhiệm đăng nhập, quản lý token và phân quyền.
- Xử lý logic ứng dụng: AWS Lambda tiếp nhận yêu cầu từ API Gateway để lưu hành trình, tải ảnh và phân tích dữ liệu.
- Quản lý dữ liệu: Amazon DynamoDB lưu thông tin chuyến đi, OpenSearch hỗ trợ tìm kiếm và truy vấn nhanh.
- Phân tích hình ảnh: Amazon Rekognition nhận diện nội dung và gắn nhãn tự động.
- Dữ liệu bản đồ & định vị: Amazon Location Service theo dõi vị trí và hiển thị bản đồ.
- Lưu trữ nội dung: Amazon S3 lưu trữ ảnh, ghi chú và dữ liệu người dùng với kích hoạt sự kiện cho Lambda.
- GGiám sát & thông báo: Amazon CloudWatch giám sát log và hiệu năng; AWS X-Ray theo dõi luồng xử lý; SNS gửi cảnh báo và thông báo đến người dùng.
- Phân phối & bảo mật web: Amazon CloudFront phân phối nội dung nhanh chóng, được bảo vệ bởi WAF, trong khi Route 53 định tuyến DNS đến toàn cầu.

### 4. Triển khai kỹ thuật  
*Các giai đoạn triển khai*  
Dự án được chia thành hai phần chính — phát triển ứng dụng web và tích hợp hạ tầng AWS — với bốn giai đoạn triển khai cụ thể:

1. Phân tích yêu cầu và thiết kế kiến trúc: Nghiên cứu các dịch vụ AWS phù hợp (CloudFront, WAF, Cognito, DynamoDB , Lambda, API Gateway, S3...) và vẽ sơ đồ kiến trúc tổng thể (Tháng 1).
2. Tính toán chi phí và mô phỏng hệ thống: Ước tính chi phí từng dịch vụ bằng AWS Pricing Calculator, thử nghiệm quy trình xử lý ảnh và vị trí để kiểm tra tính khả thi. Tối ưu kiến trúc và tài nguyên: Giảm số request, tận dụng cache CloudFront và tối ưu dung lượng S3 để giảm chi phí; tinh chỉnh Lambda và API Gateway cho hiệu năng cao (Tháng 2).
3. Phát triển, kiểm thử và triển khai: Lập trình ứng dụng web, kiểm thử bảo mật bằng WAF và giám sát hoạt động bằng CloudWatch và X-Ray (Tháng 3).

*Yêu cầu kỹ thuật*  
- Frontend: Ứng dụng web xây dựng bằng React.js, triển khai tĩnh trên Amazon S3, phân phối toàn cầu qua CloudFront giúp tăng tốc độ và giảm tải backend.
- Bảo mật & truy cập: AWS WAF chống tấn công web; Amazon Cognito quản lý xác thực người dùng (email, OAuth2).
- Backend: API Gateway tiếp nhận yêu cầu, chuyển đến AWS Lambda xử lý nghiệp vụ như ghi nhật ký, tải ảnh, truy vấn dữ liệu.
- Cơ sở dữ liệu & tìm kiếm: Amazon DynamoDB lưu dữ liệu (hành trình, nhật ký), kết hợp OpenSearch Service để lập chỉ mục và tìm kiếm nhanh.
- Phân tích ảnh: Amazon Rekognition nhận diện cảnh vật, khuôn mặt, gợi ý nhãn ảnh.
- Định vị & bản đồ: Amazon Location Service trực quan hóa tọa độ GPS trên bản đồ tương tác.
- Giám sát hệ thống: CloudWatch thu thập log, AWS X-Ray theo dõi luồng request để phát hiện lỗi và tối ưu hiệu năng. AWS Secrets Manager và AWS Certificate Manager quản lý thông tin nhạy cảm và chứng chỉ SSL/TLS.
- Thông báo: Amazon SNS gửi cảnh báo khi có lỗi hệ thống hoặc người dùng mới.

### 5. Lộ trình & Mốc triển khai  
- *Thực tập (Tháng 1–3)*:  
    - Tháng 1: Học AWS và tích lũy kiến thức 
    - Tháng 2: Thiết kế, tính chi phí và điều chỉnh kiến trúc.  
    - Tháng 3: Triển khai, kiểm thử, đưa vào sử dụng.  
- *Sau triển khai*: Nghiên cứu thêm trong vòng 1 năm.  

### 6. Ước tính ngân sách  
Có thể xem chi phí trên [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=3ac723f9e3e9041dfee17905f76cb7fd985f771d)
  

*Chi phí hạ tầng*  
- AWS Lambda: 0,01 USD/tháng
- Amazon S3: 0,13 USD/tháng
- Amazon CloudFront: 0,61 USD/tháng
- Amazon API Gateway: 0,42 USD/tháng
- Amazon DynamoDB: 0,65 USD/tháng
- Amazon Rekognition: 0,65 USD/tháng
- Amazon Location Service: 0,60 USD/tháng
- Amazon Cognito: 0,00 USD/tháng
- Amazon SNS: 0,00 USD/tháng
- Amazon CloudWatch: 1,00 USD/tháng
- Amazon X-Ray: 0,00 USD/tháng
- Amazon OpenSearch: 1,82 USD/tháng
- Amazon Route 53: 0,51 USD/tháng
  
*Tổng*: 7,30 USD/tháng, 87,60 USD/12 tháng  


### 7. Đánh giá rủi ro  
*Ma trận rủi ro*  
- Vi phạm bảo mật hoặc mất quyền truy cập người dùng: Ảnh hưởng cao, xác suất rất thấp.
- Tăng chi phí do Rikognition: Ảnh hưởng cao, xác suất trung bình
- Sai lệch dữ liệu vị trí: Ảnh hưởng cao, xác suất thấp

*Chiến lược giảm thiểu*  
- Mạng: Sử dụng Amazon CloudFront để phân phối nội dung nhanh và ổn định, hạn chế phụ thuộc vào kết nối khu vực.
- Hạ tầng: Tận dụng cơ chế tự động khởi động lại hàm Lambda và lưu cache trên trình duyệt để giảm gián đoạn dịch vụ.
- Bảo mật: Áp dụng xác thực đa lớp qua Amazon Cognito và phân quyền truy cập chặt chẽ cho tài nguyên S3.
- Chi phí: Thiết lập cảnh báo ngân sách qua AWS Budgets, tối ưu hóa Lambda và S3 theo truy cập thực tế.

*Kế hoạch dự phòng*  
- Tích hợp AWS SNS & CloudWatch Alerts để gửi thông báo ngay khi hệ thống gặp sự cố (ví dụ: lỗi Lambda, quá tải API Gateway, vượt ngân sách).
- Sử dụng CloudFormation để khôi phục nhanh toàn bộ cấu hình dịch vụ khi gặp sự cố nghiêm trọng.
- Lưu trữ bản sao dữ liệu hình ảnh và nhật ký trên S3 phiên bản sao lưu (S3 Versioning) để tránh mất mát.  

### 8. Kết quả kỳ vọng  
*Cải tiến kỹ thuật*:Ứng dụng giúp người dùng tự động lưu trữ, phân tích và hiển thị hành trình du lịch trên bản đồ thay vì ghi chép thủ công.  
*Giá trị dài hạn*:Tạo ra kho dữ liệu hành trình, hình ảnh và cảm xúc du lịch phong phú — nền tảng cho các ứng dụng gợi ý địa điểm, cá nhân hóa trải nghiệm. 