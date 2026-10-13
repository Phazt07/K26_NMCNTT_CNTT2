Phần 1:

* `>` ghi nội dung mới và xóa nội dung cũ trong file. Trong PowerShell, có thể dùng `Out-File history.txt` để ghi file mới. Thường dùng khi tạo báo cáo mới cho ca sáng.  
* `>>` thêm nội dung vào cuối file và giữ phần cũ. Lệnh tương đương là `Add-Content history.txt`. Thường dùng để ghi nhật ký liên tục, chẳng hạn theo dõi 24/7.

Phần 2:

Nếu gõ nhầm `>` thay cho `>>`, file nhật ký cũ sẽ bị ghi đè. Với nhật ký ngân hàng, những thông tin bảo trì trước đó có thể mất, khiến việc kiểm tra lịch sử hoặc tìm nguyên nhân sự cố khó hơn.

