### 1\. Vấn đề

* Tình huống: Dự án gặp lỗi xung đột cổng (Port conflict). Nhóm có hai hướng tiếp cận: dùng Google Search (tìm trên StackOverflow) hoặc dán mã lỗi vào AI Assistant để hỏi.


### 2\. Yêu cầu

* Lập bảng so sánh Ưu/Nhược điểm của Google Search và AI Assistant dựa trên 4 tiêu chí: Độ chính xác, Tính cập nhật, Khả năng giải thích, Rủi ro (Hallucination).  
* Xác định rõ trường hợp bắt buộc phải dùng Google Search để đảm bảo an toàn cho máy tính.

### 3\. Cách làm

#### Bảng so sánh Google Search vs AI Assistant

| Tiêu chí | Google Search | AI Assistant |
| :---- | :---- | :---- |
| Độ chính xác | Cao (do cộng đồng kiểm duyệt thực tế). | Khá cao nhưng có thể không tối ưu với lỗi cực kỳ mới. |
| Tính cập nhật | Cực kỳ cao, luôn có các thảo luận mới nhất. | Phụ thuộc vào dữ liệu huấn luyện của mô hình. |
| Khả năng giải thích | Thấp đến trung bình (phải tự đọc, chắt lọc nhiều bài viết). | Rất cao (tóm tắt, phân tích và hướng dẫn từng bước trực quan). |
| Rủi ro (Hallucination) | Thấp (thấy gì đọc nấy từ người thật). | Có rủi ro AI tự bịa ra các giải pháp hoặc lệnh không có thực. |

#### 

#### Trường hợp bắt buộc phải dùng Google Search

* Lỗi bảo mật nghiêm trọng/Mã độc mới xuất hiện: Khi máy tính gặp các sự cố liên quan đến lỗ hổng zero-day, mã độc tấn công (ransomware/malware) chưa từng có trong dữ liệu huấn luyện của AI, hoặc các bản vá lỗi khẩn cấp (Hotfix) vừa phát hành trong vài giờ qua. Google Search giúp bạn đọc cảnh báo chính xác từ trang chủ chính thống (như GitHub, Microsoft, CVE) để tránh làm máy tính nhiễm mã độc nặng hơn từ các lệnh sai lệch của AI.

