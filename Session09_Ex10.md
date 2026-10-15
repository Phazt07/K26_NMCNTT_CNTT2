### **Phần 1: Phân tích & Đề xuất**

1. **Đầu vào & Đầu ra:**  
   * **Đầu vào:** Trình độ sinh viên năm 1 (chưa biết lập trình), cần tìm hiểu một khái niệm kỹ thuật với giới hạn độ dài, phong cách giải thích đơn giản.  
   * **Đầu ra:** Câu trả lời ngắn gọn, đời thường, có ví dụ trực quan và loại bỏ thuật ngữ phức tạp.  
2. **Ưu \- Nhược điểm:**  
   * **Chiến lược A (Văn xuôi):**  
     * *Ưu điểm:* Nhanh, tự nhiên, tốn ít token.  
     * *Nhược điểm:* Dễ bị AI bỏ sót các ràng buộc khắt khe (độ dài, không dùng code) khi câu hỏi dài dòng.  
   * **Chiến lược B (Markdown 3 phần):**  
     * *Ưu điểm:* Rõ ràng, AI dễ bám sát cấu trúc, độ chính xác cao, dễ tái sử dụng.  
     * *Nhược điểm:* Tốn nhiều token hơn, mất thời gian soạn thảo hơn một chút.

### **Phần 2: So sánh & Lựa chọn**

3. **Bảng so sánh 4 tiêu chí:**

| Tiêu chí | Chiến lược A (Văn xuôi) | Chiến lược B (Markdown 3 phần) |
| :---- | :---- | :---- |
| **Độ chính xác** | Thấp \- Trung bình (dễ sót yêu cầu) | **Cao** (AI đọc rõ từng mục) |
| **Tiêu thụ Token** | **Thấp** (ít từ thừa) | Cao hơn (tốn ký tự cấu trúc) |
| **Khả năng tái sử dụng** | Thấp (phải viết lại từ đầu) | **Cao** (chỉ thay đổi phần khái niệm) |
| **Dễ học cho người mới** | **Cao** (gõ như văn nói) | Trung bình (cần biết phân chia bố cục) |

4.   
   **Chốt lựa chọn:**  
   * **Dùng Chiến lược A:** Khi tra cứu nhanh, câu hỏi đơn giản, không có nhiều ràng buộc khắt khe về định dạng hay độ dài.  
   * **Dùng Chiến lược B:** Khi cần hỏi các bài tập lớn, tài liệu kỹ thuật, hoặc khi câu hỏi có nhiều ràng buộc phức tạp (như bài tập này) để đảm bảo AI không trả lời lan man.

### **Phần 3: Thiết kế & Triển khai**

5. **Prompt mẫu hỏi về khái niệm 'Token' (dùng Chiến lược B):**

\#\# Bối cảnh  
Tôi là sinh viên năm 1 PTIT, chưa có nền tảng lập trình.

\#\# Khái niệm cần giải thích  
Token trong AI và ngôn ngữ Markdown

\#\# Yêu cầu  
\- Dùng ngôn ngữ đời thường, so sánh với vật dụng quen thuộc (như từ vựng hoặc mảnh ghép)  
\- Giải thích trong khoảng 100-150 từ  
\- Cho 1 ví dụ minh họa cụ thể

\#\# Không cần  
\- Thuật ngữ kỹ thuật phức tạp về toán học hay xử lý ngôn ngữ tự nhiên

6\. **Trả lời 2 bẫy dữ liệu:**

* **Bẫy 1 (Đặt sai nội dung vào cấu trúc):** AI vẫn có khả năng đọc hiểu tổng thể nhưng sẽ dễ bị bối rối, xử lý không đúng trọng tâm (ví dụ: nhầm lẫn giữa phần Bối cảnh và Yêu cầu), dẫn đến việc câu trả lời không tuân thủ chính xác các ràng buộc (độ dài, phong cách diễn đạt).  
* **Bẫy 2 (Khi nào ưu tiên chiến lược A):** Nên ưu tiên chiến lược A khi cần đặt câu hỏi nhanh, giao tiếp thông thường với AI, hoặc khi tài nguyên token/chi phí cần tối ưu hóa tối đa cho các tác vụ đơn giản, không yêu cầu cấu trúc phức tạp.

