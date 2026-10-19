**Phần 1: SRS (Word)**

* **Cấu trúc Heading:** Gán Heading 1 (1, 2, 3), Heading 2 (1.1, 1.2, 2.1, 2.2), Heading 3 (2.1.1).  
* **Mô tả ngắn:**  
  * *Chức năng:* Cho phép sinh viên tra cứu và đăng ký mượn/trả sách trực tuyến.  
  * *Bảo mật:* Mã hóa mật khẩu người dùng và phân quyền truy cập theo vai trò.  
* **Auto TOC:** Chèn mục lục tự động và cập nhật lại số trang sau khi ngắt trang.

### **Phần 2: Chuẩn hóa dữ liệu & AutoFilter (Excel)**

* **3 Lỗi vi phạm 5 Quy tắc Vàng:**  
  * Hàng 1: Merge ô tiêu đề (DANH SÁCH...).  
  * Hàng 5: Có hàng trống hoàn toàn.  
  * Hàng 6: Chứa dòng tổng cộng nằm trong vùng dữ liệu.  
* **Record & Field:**  
  * *Record (Dòng):* Thông tin của 1 phiếu mượn (VD: SV001 | Nguyễn Văn An | S001 | 01/10/2026 | Đang mượn).  
  * *Field (Cột):* Thuộc tính dữ liệu (VD: cột MSSV hoặc Tình Trạng).  
* **Lọc dữ liệu:** Bấm Ctrl+Shift+L và chọn lọc cột Tình trạng là "Quá hạn".

### **Phần 3: VLOOKUP**

* **Công thức ô F3 (Tên Sách):**  
* $=VLOOKUP(C3,DanhMucSach!$A$2:$C$4,2,FALSE)$  
* **Lỗi mã** S099 **(Hàng 8):** Trả về lỗi \#N/A vì mã S099 không tồn tại trong bảng tra cứu DanhMucSach.  
* **Công thức bọc IFERROR:**  
* $=IFERROR(VLOOKUP(C3,DanhMucSach!$A$2:$C$4,2,FALSE),"Khôngtìmthấysách")$

### **Phần 4: Slide Báo Cáo**

* **Assertion Title:** *"Hệ thống quản lý thư viện đã số hóa thành công và chuẩn hóa toàn bộ dữ liệu mượn sách"*  
* **Content Area:** 100% dữ liệu phiếu mượn tháng 10 đã được làm sạch và nối thành công với danh mục sách.  
* **Biểu đồ đề xuất:** **Bar Chart** (Biểu đồ thanh ngang) để so sánh số lượng sách theo từng trạng thái (*Đang mượn, Quá hạn, Đã trả*).  
* **Rule 10/20/30:** Slide này nằm trong tổng số 10 slides và thời gian trình bày dự kiến là **2 phút**.

