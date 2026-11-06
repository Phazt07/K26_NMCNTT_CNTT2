### Phần 1: Thiết kế Prompt 3 Thành phần Chuẩn hóa

#### 1\. Vấn đề

* Nguyên nhân: Câu hỏi chung chung thiếu hoàn toàn bối cảnh kỹ thuật, hệ điều hành và log lỗi khiến AI bị rơi vào tình trạng Ảo giác (AI Hallucination) – đoán mò nguyên nhân phần cứng và đưa ra giải pháp phá hoại (tháo vỏ sắt).

#### 2\. Yêu cầu

* Xây dựng câu Prompt 3 thành phần chuẩn kỹ sư dựa trên log lỗi thực tế của trạm sạc.

#### 3\. Cách làm

\[Context\] Tôi đang vận hành phần mềm trạm sạc điện VoltCharge trên hệ điều hành Windows 11\.

\[Raw Error\] System.UnauthorizedAccessException: Access to the path 'C:\\Program Files\\VoltCharge\\data\\session.log' is denied. Process terminated with exit code 5\.

\[Instruction\] Hãy dịch lỗi này sang tiếng Việt dễ hiểu và cung cấp 3 bước khắc phục ngắn gọn nhất.

### Phần 2: Giải mã Lỗi & Kịch bản Khắc phục

#### 1\. Vấn đề

* Dịch nghĩa & Nguyên nhân gốc rễ: Lỗi Access is denied (Mã lỗi 5\) nghĩa là ứng dụng không có quyền ghi file log vào thư mục được bảo vệ của hệ thống (C:\\Program Files).

#### 2\. Yêu cầu

* Hướng dẫn 3 bước xử lý tại chỗ trên Windows 11 và cách xử lý bẫy an ninh thông tin khi dùng AI.

#### 3\. Cách làm

* 3 bước xử lý tại chỗ:  
  * Tắt tiến trình cũ: Mở Task Manager (Ctrl \+ Shift \+ Esc), tìm và dừng tiến trình ControllerDaemon đang treo.  
  * Chạy quyền Admin: Nhấp chuột phải vào biểu tượng ứng dụng VoltCharge $\rightarrow$ Chọn Run as administrator.  
  * Cấp quyền thư mục (nếu cần): Nhấp chuột phải vào thư mục C:\\Program Files\\VoltCharge\\data $\rightarrow$ Chọn Properties $\rightarrow$ Thẻ Security $\rightarrow$ Cấp quyền Full control cho tài khoản vận hành.  
* Xử lý bẫy an ninh (API\_KEY):  
  * Cách xử lý: Phải xóa hoặc thay thế chuỗi bí mật bằng ký tự giả lập (ví dụ: API\_KEY: \[REDACTED\] hoặc volt\_secret\_token\_\*\*\*\*) trước khi dán lên AI.  
  * Lý do: Tuyệt đối không để lộ các khóa bảo mật (Secret/API Key) lên không gian mạng công cộng để tránh kẻ gian đánh cắp quyền truy cập hệ thống trạm sạc.

