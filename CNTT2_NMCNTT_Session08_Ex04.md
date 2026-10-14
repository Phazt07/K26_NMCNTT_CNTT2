Phần 1: So sánh

Dấu `>` ghi kết quả mới vào file và xóa nội dung cũ. Trong PowerShell, nó tương đương với `Out-File`. Có thể dùng khi muốn tạo báo cáo mới, chẳng hạn báo cáo riêng cho ca sáng.

Dấu `>>` thêm kết quả vào cuối file và giữ nội dung cũ. Nó tương đương với `Out-File -Append`. Phù hợp để ghi nhật ký liên tục trong ngày hoặc theo dõi 24/7.

Theo đề bài, `Out-File` mặc định ghi file bằng UTF-16. Nếu cần chọn encoding UTF-8, có thể dùng `Add-Content -Encoding utf8`.

Nếu cuối tháng An gõ nhầm `>` thay vì `>>`, báo cáo của 30 ngày trước sẽ bị xóa và thay bằng kết quả mới. Vì vậy, lịch sử lỗi có thể bị mất.

Phần 2: Cách ghi nhật ký lỗi liên tục

Get-Content server.log | Select-String "ERROR" |  
    Add-Content \-Path daily\_report.txt \-Encoding utf8

Lệnh này tìm các dòng có chữ `ERROR` rồi thêm chúng vào cuối file `daily_report.txt`.

