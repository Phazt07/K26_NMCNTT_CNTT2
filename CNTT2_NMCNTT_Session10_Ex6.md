### **Phần 1\. Phân tích**

**2 sai lầm của Nam:**

1. **Dùng file Rich Text (`.docx`) lưu mã nguồn/tài liệu kỹ thuật:** File Word là dạng nhị phân (binary), GitHub không thể đọc trực tiếp trên trình duyệt mà phải tải về, và Git cũng không so sánh (diff) được chi tiết từng dòng mà chỉ coi là cục dữ liệu khổng lồ thay đổi.  
2. **Không hiểu về cơ chế Conflict của Git:** Chỉ sửa một dấu phẩy nhỏ trong file Word, Git cũng tính là đổi toàn bộ file, dẫn đến xung đột khi nhóm cùng làm việc.

**Tại sao Markdown an toàn và nhẹ hơn?**

* **Là văn bản thô (Plain Text):** Chỉ chứa ký tự chữ thông thường nên cực kỳ nhẹ, không sợ lỗi cấu trúc.  
* **Chống mất dữ liệu (Bẫy 1 byte):** Nếu file Word mất 1 byte, toàn bộ file `.docx` (thực chất là file nén zip) sẽ hỏng hoàn toàn không mở được. Ngược lại, Markdown mất 1 byte thì chỉ mất đúng ký tự đó, các phần còn lại vẫn đọc và cứu lại bình thường.  
* **Tối ưu cho Git:** GitHub tự động render đẹp mắt, Git dễ dàng bắt lỗi (diff) từng dòng khi nhóm sửa đổi.

### **Phần 2\. Nội dung file `README.md` (mẫu mẫu để đẩy lên GitHub)**

\# Dự án GreenTech

\#\# Giới thiệu  
Chào mọi người, đây là tài liệu giới thiệu dự án "GreenTech" của nhóm chúng mình nhằm quản lý và tối ưu hóa năng lượng xanh.

\#\# Thành viên nhóm  
\* Nam (PTIT)  
\* Các thành viên khác...  
