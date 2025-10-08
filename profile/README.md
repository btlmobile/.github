# SeaWhisper - Ứng dụng chia sẻ tâm sự ẩn danh

## Tổng quan dự án

SeaWhisper là một ứng dụng mobile cho phép người dùng chia sẻ tâm sự một cách ẩn danh thông qua việc "thả chai" và nhận phản hồi từ cộng đồng. Ứng dụng tập trung vào việc tạo ra một không gian an toàn, không toxic để người dùng có thể giải tỏa cảm xúc.

## Problem Statement

### Pain Points từ khảo sát:

- Người trẻ có nhu cầu chia sẻ tâm sự nhưng sợ bị phán xét
- Các ứng dụng ẩn danh hiện có (YikYak, Whisper, NGL…) thường toxic, ít kiểm duyệt
- Mạng xã hội công khai khiến nhiều người mất an toàn tâm lý

### Insight từ khảo sát:

- 80% người dùng mong muốn "an toàn, không toxic"
- 60% thích app có cảm giác bí ẩn, nhẹ nhàng
- 45% từng bị ảnh hưởng cảm xúc sau khi dùng app ẩn danh khác
- Nhiều người từng xóa app ẩn danh vì bị toxic

## Solution

SeaWhisper cung cấp:

- Cho phép "thả chai" tâm sự (text, audio, hoặc sticker)
- "Người lạ" ngẫu nhiên nhặt chai, có thể chọn gửi lại phản hồi an ủi
- Sử dụng AI filter (sentiment analysis + toxic detection) để loại bỏ nội dung tiêu cực
- Có chế độ thư mục cảm xúc, nơi người dùng lưu lại chai mình từng nhận
- Không dùng ranking/like → giảm so sánh xã hội
- Cộng đồng nhỏ, được kiểm duyệt bởi AI và tính năng report

## User Stories

### Epic 1: Quản lý tài khoản người dùng

**As a** người dùng mới  
**I want to** tạo tài khoản ẩn danh đơn giản  
**So that** tôi có thể sử dụng ứng dụng mà không lo lộ danh tính

**As a** người dùng  
**I want to** đăng nhập/đăng xuất dễ dàng  
**So that** tôi có thể truy cập ứng dụng một cách thuận tiện

### Epic 2: Thả chai tâm sự

**As a** người dùng có tâm sự  
**I want to** thả chai với nội dung text  
**So that** tôi có thể chia sẻ suy nghĩ của mình

**As a** người dùng muốn biểu đạt cảm xúc  
**I want to** thả chai với giọng nói  
**So that** tôi có thể truyền tải cảm xúc qua giọng nói

**As a** người dùng muốn gửi tin nhắn ngắn  
**I want to** thả chai với sticker/emoji  
**So that** tôi có thể biểu đạt cảm xúc một cách nhanh chóng

**As a** người dùng quan tâm đến quyền riêng tư  
**I want to** chọn chế độ hiển thị chai (công khai/riêng tư)  
**So that** tôi có thể kiểm soát ai có thể thấy chai của mình

### Epic 3: Nhặt chai và phản hồi

**As a** người dùng muốn giúp đỡ người khác  
**I want to** nhặt chai ngẫu nhiên từ biển  
**So that** tôi có thể đọc và hiểu tâm sự của người khác

**As a** người dùng muốn an ủi người khác  
**I want to** gửi phản hồi tích cực cho chai tôi nhặt  
**So that** tôi có thể giúp người khác cảm thấy tốt hơn

**As a** người dùng không biết phản hồi như thế nào  
**I want to** bỏ qua chai mà không phản hồi  
**So that** tôi không cảm thấy áp lực phải trả lời

### Epic 4: Quản lý chai đã nhận

**As a** người dùng muốn lưu lại những điều ý nghĩa  
**I want to** lưu chai vào thư mục cảm xúc  
**So that** tôi có thể đọc lại những tin nhắn tích cực khi cần

**As a** người dùng  
**I want to** xem lại lịch sử chai đã nhặt  
**So that** tôi có thể theo dõi những chai mình đã tương tác

### Epic 5: Bảo vệ cộng đồng

**As a** người dùng muốn môi trường an toàn  
**I want to** báo cáo nội dung toxic hoặc không phù hợp  
**So that** tôi có thể giúp duy trì cộng đồng lành mạnh

**As a** người dùng  
**I want to** AI tự động lọc nội dung tiêu cực  
**So that** tôi không phải tiếp xúc với nội dung có hại

## Functional Requirements

### FR1: Quản lý tài khoản

- **FR1.1**: Người dùng có thể đăng ký tài khoản với username ẩn danh
- **FR1.2**: Người dùng có thể đăng nhập bằng username và mật khẩu
- **FR1.3**: Người dùng có thể đổi mật khẩu
- **FR1.4**: Người dùng có thể xóa tài khoản

### FR2: Chức năng thả chai

- **FR2.1**: Người dùng có thể tạo chai với nội dung text (tối đa 500 ký tự)
- **FR2.2**: Người dùng có thể ghi âm và gửi chai dưới dạng audio (tối đa 2 phút)
- **FR2.3**: Người dùng có thể chọn sticker/emoji từ thư viện có sẵn
- **FR2.4**: Người dùng có thể chọn chế độ hiển thị: công khai hoặc riêng tư
- **FR2.5**: Hệ thống kiểm tra nội dung chai trước khi cho phép thả

### FR3: Chức năng nhặt chai

- **FR3.1**: Người dùng có thể nhặt chai ngẫu nhiên từ biển
- **FR3.2**: Mỗi chai chỉ có thể được nhặt bởi một người dùng
- **FR3.3**: Người dùng có thể đọc/xem/nghe nội dung chai đã nhặt
- **FR3.4**: Người dùng có thể quyết định phản hồi hoặc bỏ qua chai

### FR4: Chức năng phản hồi

- **FR4.1**: Người dùng có thể gửi phản hồi text cho chai đã nhặt
- **FR4.2**: Người dùng có thể gửi phản hồi audio cho chai đã nhặt
- **FR4.3**: Người dùng có thể gửi sticker/emoji làm phản hồi
- **FR4.4**: Phản hồi được gửi ẩn danh đến người thả chai

### FR5: Quản lý chai

- **FR5.1**: Người dùng có thể lưu chai vào thư mục cảm xúc
- **FR5.2**: Người dùng có thể xem lịch sử chai đã nhặt
- **FR5.3**: Người dùng có thể xem lịch sử chai đã thả
- **FR5.4**: Người dùng có thể xóa chai khỏi thư mục cảm xúc

### FR6: Báo cáo và kiểm duyệt

- **FR6.1**: Người dùng có thể báo cáo chai hoặc phản hồi không phù hợp
- **FR6.2**: Hệ thống AI tự động phát hiện và lọc nội dung toxic
- **FR6.3**: Admin có thể xem và xử lý các báo cáo từ người dùng
- **FR6.4**: Hệ thống tự động ẩn nội dung vi phạm chính sách

## Non-Functional Requirements

### NFR1: Hiệu suất

- **NFR1.1**: Thời gian phản hồi của ứng dụng ≤ 2 giây
- **NFR1.2**: Thời gian tải chai mới ≤ 3 giây
- **NFR1.3**: Ứng dụng hỗ trợ tối thiểu 1000 người dùng đồng thời
- **NFR1.4**: Dung lượng ứng dụng ≤ 50MB

### NFR2: Bảo mật và quyền riêng tư

- **NFR2.1**: Tất cả dữ liệu người dùng được mã hóa end-to-end
- **NFR2.2**: Không lưu trữ thông tin cá nhân thực của người dùng
- **NFR2.3**: Có cơ chế xác thực 2 lớp cho tài khoản
- **NFR2.4**: Dữ liệu được backup định kỳ và có thể khôi phục

### NFR3: Khả năng sử dụng

- **NFR3.1**: Giao diện người dùng đơn giản, dễ sử dụng
- **NFR3.2**: Thời gian học cách sử dụng ứng dụng ≤ 5 phút
- **NFR3.3**: Ứng dụng hỗ trợ tiếng Việt hoàn toàn
- **NFR3.4**: Giao diện thân thiện với người dùng mù màu

### NFR4: Tính khả dụng

- **NFR4.1**: Thời gian hoạt động của hệ thống ≥ 99.5%
- **NFR4.2**: Có cơ chế failover tự động khi server gặp sự cố
- **NFR4.3**: Thời gian khôi phục sau sự cố ≤ 1 giờ

### NFR5: Khả năng mở rộng

- **NFR5.1**: Kiến trúc hệ thống có thể mở rộng để hỗ trợ nhiều người dùng hơn
- **NFR5.2**: Database có thể scale theo chiều ngang
- **NFR5.3**: API có thể tích hợp với các dịch vụ bên thứ 3

### NFR6: Tương thích

- **NFR6.1**: Hỗ trợ iOS 12.0 trở lên
- **NFR6.2**: Hỗ trợ Android 8.0 (API level 26) trở lên
- **NFR6.3**: Ứng dụng hoạt động tốt trên các kích thước màn hình khác nhau
- **NFR6.4**: Hỗ trợ cả chế độ sáng và tối

### NFR7: Tính bền vững

- **NFR7.1**: Tiêu thụ pin điện thoại tối thiểu
- **NFR7.2**: Sử dụng dữ liệu di động hiệu quả
- **NFR7.3**: Hỗ trợ hoạt động offline cơ bản (xem chai đã lưu)

## Technology Stack

### Frontend

- React Native cho mobile app
- Redux cho state management
- React Navigation cho điều hướng

### Backend

- Node.js với Express.js
- MongoDB cho database
- Redis cho caching
- Socket.io cho real-time communication

### AI/ML

- TensorFlow.js cho sentiment analysis
- Custom toxic detection model
- Natural Language Processing cho tiếng Việt

### Infrastructure

- AWS/GCP cho hosting
- CloudFront cho CDN
- CloudWatch cho monitoring

## Roadmap

### Phase 1 (MVP) - 3 tháng

- Chức năng cơ bản: thả chai, nhặt chai, phản hồi
- AI filter cơ bản
- Giao diện đơn giản

### Phase 2 - 2 tháng

- Thư mục cảm xúc
- Cải thiện AI filter
- Báo cáo và kiểm duyệt

### Phase 3 - 2 tháng

- Tính năng nâng cao
- Tối ưu hiệu suất
- Mở rộng cộng đồng

---

_Dự án được phát triển bởi team BTL Mobile - 2024_
