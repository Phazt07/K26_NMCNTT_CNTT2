### **1\. Vấn đề**

AI đưa ra lệnh Terminal để sửa lỗi **“Path not found”** khi cài Python. Lệnh lạ có thể sai hoặc gây ảnh hưởng đến hệ thống.

### **2\. Yêu cầu**

Dùng mô hình **IPO** để kiểm chứng lệnh và viết prompt yêu cầu AI giải thích độ an toàn trước khi chạy.

### **3\. Cách làm**

* **Input:** Ghi lại chính xác lệnh AI đề xuất, hệ điều hành và phiên bản Python liên quan.  
* **Process:** Tìm nguyên văn lệnh bằng toán tử `site:stackoverflow.com` hoặc tra tài liệu chính thức của Python/hệ điều hành. Kiểm tra lệnh làm gì, có yêu cầu quyền quản trị hay xóa/sửa tệp không, và có phù hợp với phiên bản của bạn không.  
* **Output:** Chỉ đánh giá lệnh **an toàn** nếu mục đích và tác động được xác nhận từ nguồn đáng tin cậy. Nếu không tìm thấy xác nhận hoặc chưa hiểu rõ tác động, **không chạy lệnh**.

**Prompt hỏi ngược AI:**

> Hãy giải thích từng phần của lệnh `[dán lệnh]`: lệnh thay đổi những gì, có cần quyền quản trị không, và có thể gây mất dữ liệu hoặc ảnh hưởng hệ thống không? Lệnh này có phù hợp với `[hệ điều hành và phiên bản]` không? Hãy dẫn nguồn tài liệu chính thức để kiểm chứng. Nếu không chắc chắn, hãy nói rõ và đề xuất cách kiểm tra an toàn trước khi chạy.

