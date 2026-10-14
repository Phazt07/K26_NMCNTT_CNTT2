### **Phần 1: Thiết kế kiến trúc PowerShell Script**

4 khối cấu trúc trong mã nguồn:

1. **Header block:** Chứa thông tin mô tả script, tác giả và ngày tạo dưới dạng chú thích (`#`).  
2. **Biến cấu hình:** Khai báo đường dẫn tệp log nguồn và tệp báo cáo đầu ra bằng tiền tố `$`.  
3. **Thông báo tiến trình:** Sử dụng `Write-Host` để hiển thị trạng thái xử lý trực tiếp ra màn hình terminal.  
4. **Logic xử lý:** Đọc file (`Get-Content`), lọc lỗi qua Pipeline (`Select-String`) và ghi kết quả vào tệp (`>>`).

### **Phần 2: Tệp mã nguồn `auto_report.ps1` hoàn chỉnh**

\<\#  
.SYNOPSIS  
    Script tự động lọc lỗi 404 từ file log và tạo báo cáo.  
.AUTHOR  
    Lã Đức Phát  
\#\>

\$duong\_dan\_log \= "server.log"  
\$file\_bao\_cao \= "report.txt"

Write-Host "Dang loc loi 404..." \-ForegroundColor Yellow

"=== HE THONG TU DONG LOC LOG \===" | Out-File \-FilePath \$file\_bao\_cao \-Encoding utf8  
Get-Content \-Path \$duong\_dan\_log | Select-String "404" | Out-File \-FilePath \$file\_bao\_cao \-Append \-Encoding utf8

Write-Host "Hoan tat\!" \-ForegroundColor Green  
