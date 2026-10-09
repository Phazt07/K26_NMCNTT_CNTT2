Báo cáo thực hành PowerShell: Smart-Farm  
1\. Phân tích luồng IPO  
Input: Thư mục Home (\~), Public, file mẫu template.ps1, thông tin pass.

Process: Tạo thư mục, tạo file .env, copy/đổi tên file script, kiểm tra lại cấu trúc.

Output: Cây thư mục smart-farm hoàn chỉnh (bin, config, data), file .env và pump\_control.ps1.

2\. Nhật ký lệnh PowerShell  
Bước 1 (Tạo 3 thư mục trong 1 lệnh):  
mkdir \~/smart-farm/bin, \~/smart-farm/config, \~/smart-farm/data

Bước 2 Tạo file ẩn .env:  
"PASS=123456" \> \~/smart-farm/config/.env

Bước 3 Copy và đổi tên file trong 1 lệnh:  
cp C:\\Users\\Public\\template.ps1 \~/smart-farm/bin/pump\_control.ps1

Bước 4 Kiểm tra lại toàn bộ thư mục:  
ls \~/smart-farm \-Recurse \-Force

3\. Xử lý lỗi "Access to the path is denied"  
Start-Process powershell \-Verb RunAs