Phần 1: Googling đúng cách

* Vấn đề: Câu hỏi "văn nói" (tại sao em cài node xong mà gõ npm nó không nhận vậy thầy ơi) chứa nhiều từ ngữ thừa thãi, cảm tính, không có từ khóa kỹ thuật chính xác khiến Google không phân loại được lỗi hệ thống.  
* Yêu cầu: Bóc tách lỗi và viết 3 câu truy vấn tối ưu với các toán tử site:, " ", \-.  
* Cách làm:  
  * Bóc tách lỗi: Tên phần mềm/HĐH: Node.js / Windows 11 \| Mã lỗi: 'npm' is not recognized as an internal or external command \| Thao tác: Gõ lệnh npm \-v trong Terminal.  
  * 3 câu truy vấn:  
    1. site:stackoverflow.com npm is not recognized as an internal or external command  
    2. "npm is not recognized as an internal or external command"  
    3. npm is not recognized windows 11 \-xp

### Phần 2: Thẩm định StackOverflow

* Vấn đề: Cần phân biệt câu trả lời chất lượng (Câu A) và câu trả lời lỗi thời, nguy hiểm (Câu B) dựa trên tiêu chí uy tín và quy trình đọc lướt.  
* Yêu cầu: So sánh 2 câu trả lời, chọn phương án đúng và nêu quy trình 30 giây đọc lướt.  
* Cách làm:  
  * So sánh:  
    * Câu trả lời A: Vote/Tích xanh: \+186 & Accepted Answer \| Thời gian: 2 năm trước \| Tags: Khớp \[node.js\] \[windows\] \[npm\].  
    * Câu trả lời B: Vote/Tích xanh: \+2 & Không có tích xanh \| Thời gian: 9 năm trước \| Tags: Lệch \[windows-xp\].  
  * Kết luận & Cảnh báo: Áp dụng Câu trả lời A. Câu trả lời B là "bẫy" nguy hiểm vì dùng cho Windows XP cũ kỹ, nếu làm theo có thể làm hỏng driver mạng hiện tại.  
  * Quy trình 30 Giây Đọc lướt: Nhìn tiêu đề/Tags \-\> Xem điểm Vote & Tích xanh (Accepted Answer) \-\> Đọc ngay phần nội dung Code/Giải pháp được đánh dấu xanh \-\> Đọc bình luận (Comments) bên dưới nếu có.

### Phần 3: Hỏi AI đúng cách và nhận diện rủi ro

* Vấn đề: Lỗi vẫn còn sau khi thêm PATH, AI đưa ra một câu trả lời độc hại (del /f /s /q C:\\Windows\\System32\\\*).  
* Yêu cầu: Viết Prompt 3 thành phần, áp dụng 3 Nguyên tắc An toàn Vàng và đưa ra cách phản hồi AI.  
* Cách làm:  
  * Prompt 3 Thành phần:  
  * "Tôi đang dùng Windows 11, mới cài Node.js. Khi gõ npm \-v trong Terminal của VS Code, máy báo lỗi: 'npm' is not recognized as an internal or external command. Tôi đã thử thêm đường dẫn vào biến môi trường PATH nhưng lỗi vẫn còn. Hãy hướng dẫn tôi cách khắc phục triệt để lỗi này."  
  * Nhận diện rủi ro: Lệnh AI đưa ra yêu cầu xóa thư mục hệ thống (System32), vi phạm nghiêm trọng Nguyên tắc An toàn Vàng (lệnh phá hoại hệ điều hành).  
  * Cách phản hồi AI: Từ chối lệnh, đồng thời cảnh báo AI: "Lệnh bạn vừa cung cấp sẽ xóa các tệp hệ thống quan trọng trong System32 và làm hỏng máy tính. Vui lòng cung cấp giải pháp an toàn khác liên quan đến cấu hình biến môi trường PATH hoặc quyền npm."

### Phần 4: Viết Bug Report chuẩn để nhờ hỗ trợ

* Vấn đề: Cần chuyển đổi thông tin lỗi thành một báo cáo chuẩn kỹ thuật để nhờ trợ giảng hỗ trợ nhanh chóng và chuyên nghiệp.  
* Yêu cầu: Viết tin nhắn kém vs tin nhắn chuẩn (4 mảnh ghép), nêu phím tắt chụp màn hình và lưu ý bảo mật.  
* Cách làm:  
  * Tin nhắn Kém: "Thầy ơi máy em bị lỗi không gõ được npm, giúp em với."  
  * Tin nhắn Chuẩn (Bug Report):  
    * Context: Cài Node.js trên Windows 11 mới, mở VS Code Terminal kiểm tra.  
    * Expected: Hiển thị phiên bản npm (ví dụ: v10.x.x).  
    * Actual: Báo lỗi không nhận lệnh và vẫn lỗi sau khi đã cấu hình PATH theo hướng dẫn trên StackOverflow.  
    * Log & Screenshot: 'npm' is not recognized as an internal or external command, operable program or batch file. \+ Kèm hình ảnh Terminal.  
  * Phím tắt & Bảo mật:  
    * Phím tắt chụp màn hình Windows: Windows \+ Shift \+ S.  
    * Lưu ý bảo mật: Không để lộ các thông tin cá nhân nhạy cảm như mật khẩu, token API, email cá nhân hoặc đường dẫn chứa tên tài khoản Windows (nếu có thông tin riêng tư) khi chụp ảnh màn hình.

