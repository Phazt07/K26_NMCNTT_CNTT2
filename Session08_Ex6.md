### **Phần 1: Phân tích mã nguồn nguy hiểm từ AI**

* **Điểm cực kỳ nguy hiểm:** Lệnh `Remove-Item -Path "C:\*" -Recurse -Force` quét và xóa toàn bộ ổ đĩa gốc `C:\`, bao gồm cả hệ điều hành Windows và các tệp hệ thống quan trọng.  
* **Ý nghĩa tham số:**  
  * `-Path "C:\*"`: Chỉ định toàn bộ thư mục và tệp gốc trong ổ C.  
  * `-Recurse`: Quét và xóa đệ quy toàn bộ thư mục con bên trong.  
  * `-Force`: Ép buộc xóa cả các tệp ẩn, tệp hệ thống hoặc tệp đang bị khóa mà không cần hỏi lại.  
* **Hậu quả:** Sập hoàn toàn hệ điều hành, máy tính không thể khởi động, mất toàn bộ dữ liệu.  
* **3 Nguyên tắc Vàng thẩm định:** 1\. Không bao giờ chạy lệnh xóa trực tiếp trên thư mục gốc (`C:\`). 2\. Luôn kiểm tra kỹ đường dẫn tham số (`-Path`). 3\. Thử nghiệm trước ở thư mục giả lập (sandbox).

### **Phần 2: Triển khai Script an toàn (`safe_cleanup.ps1`)**

PowerShell  
\<\#  
.SYNOPSIS  
    Script bảo trì hệ thống an toàn cho Trang trại Lan thông minh.  
.AUTHOR  
    Lã Đức Phát  
\#\>

\# 1\. Di chuyển đến thư mục logs của dự án  
Set-Location \-Path "./logs"

\# 2\. Lọc các dòng có chữ WARNING từ system.log ra tệp issues.txt  
Get-Content \-Path "system.log" | Select-String "WARNING" | Out-File \-FilePath "issues.txt" \-Encoding utf8

\# 3\. Chỉ xóa các tệp .tmp bên trong thư mục dự án với phạm vi giới hạn  
Remove-Item \-Path "\*.tmp" \-Force

### **Phần 3: Kiểm thử trên PowerShell**

* **Xem nội dung tệp báo cáo:**  
* PowerShell

Get-Content issues.txt

* **Xác nhận tệp `.tmp` đã bị xóa:**  
* PowerShell

Get-ChildItem

* **Kiểm tra nhanh tệp báo cáo tồn tại:**  
* PowerShell  
* Test-Path issues.txt

