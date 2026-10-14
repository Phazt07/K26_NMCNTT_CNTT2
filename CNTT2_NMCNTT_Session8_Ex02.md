## **Phần 1: Phân tích**

* **Nhầm lẫn của An:** Nhầm giữa việc tìm kiếm tệp tin (cấu trúc hệ thống) với tìm kiếm nội dung bên trong tệp (dữ liệu).  
* **Phân biệt:**  
  * `Get-ChildItem`: Dùng để liệt kê/tìm các tệp hoặc thư mục dựa trên tên, phần mở rộng, thuộc tính đường dẫn.  
  * `Select-String`: Dùng để tìm kiếm văn bản hoặc từ khóa bên trong nội dung của tệp (tương tự `grep` trên Linux).

## **Phần 2: Hoàn thiện**

Câu lệnh PowerShell chuẩn:

      Select-String \-Path "access.log" \-Pattern "error"