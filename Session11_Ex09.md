### **Phần 1: Phân tích bài toán & Giải pháp**

**1\. Bảng I/O:**

| Cột cần điền | Lookup\_value | Table\_array | Col\_index\_num |
| :---- | :---- | :---- | :---- |
| **D (Tên TG)** | Mã tác giả (C2) | Sheet "DanhMucTacGia"\!A:E | 2 |
| **E (Phòng)** | Mã tác giả (C2) | Sheet "DanhMucTacGia"\!A:E | 4 |
| **F (Thù lao)** | Mã tác giả (C2) | Sheet "DanhMucTacGia"\!A:E | 5 |

**2\. Chiến lược xử lý bẫy:**

* **Bẫy khoảng trắng:** Dùng hàm TRIM(C2) để xóa khoảng trắng thừa.  
*   
* **Bẫy lỗi \#N/A:** Dùng IFERROR(..., "Chưa cập nhật") bọc bên ngoài.  
*   
* **Bẫy trôi vùng:** Dùng ký tự \$ để cố định vùng dữ liệu (ví dụ: 'DanhMucTacGia'\!$A$2:$E$100).  
* 

**3\. Các bước thực hiện:**

1. Chọn ô D2, nhập công thức tra cứu Tên tác giả kết hợp chống lỗi.  
2.   
3. Kéo (fill) công thức từ D2 xuống cuối bảng (D81).  
4.   
5. Copy công thức sang cột E và F, chỉ cần thay đổi số thứ tự cột (col\_index\_num thành 4 và 5).  
6. 

### **Phần 2: Công thức và Giải thích**

**4\. Công thức ô D2 (Tên Tác Giả):**  
\$\$=IFERROR(VLOOKUP(TRIM(C2), 'DanhMucTacGia'\!$A$2:$E$100, 2, FALSE), "Chưa cập nhật")\$\$

**5\. Công thức ô E2 (Phòng) & F2 (Thù lao):**

* **Ô E2 (Phòng):**  
* \$\$=IFERROR(VLOOKUP(TRIM(C2), 'DanhMucTacGia'\!$A$2:$E$100, 4, FALSE), "Chưa cập nhật")\$\$  
*   
* **Ô F2 (Thù lao):**  
* \$\$=IFERROR(VLOOKUP(TRIM(C2), 'DanhMucTacGia'\!$A$2:$E$100, 5, FALSE), "Chưa cập nhật")\$\$  
*   
* *Giải thích:* Cấu trúc giữ nguyên vì vẫn tìm kiếm dựa trên mã tác giả và cùng bảng dữ liệu, chỉ thay đổi số thứ tự cột (col\_index\_num) tương ứng với vị trí cột cần lấy thông tin (Cột 4 là Phòng, Cột 5 là Thù lao).  
* 

**6\. Hiện tượng khi bỏ dấu** \$**:**

* Nếu không có dấu \$, khi kéo công thức từ D2 xuống D5, vùng tra cứu sẽ bị trôi theo số dòng:  
* 

  * Ô D2: tra cứu ở $A$2:$E$100 (đúng).  
  *   
  * Ô D5: vùng tra cứu bị dịch xuống thành $A$5:$E$103 (sai/lệch dòng đầu). Kết quả sẽ bỏ sót các tác giả ở dòng đầu bảng tra.

