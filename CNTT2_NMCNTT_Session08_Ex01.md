## **Phần 1: Phân tích**

* **Notepad bị "Not Responding":** Do Notepad tải toàn bộ tệp 800MB vào RAM để hiển thị, gây quá tải và tràn bộ nhớ.  
* **Lệnh `cat` lỗi trên CMD:** CMD là công cụ dòng lệnh cũ, không tích hợp sẵn lệnh `cat` (vốn thuộc hệ sinh thái Unix/Linux).  
* **Lệnh `cat` chạy được trên PowerShell:** Do PowerShell hỗ trợ cơ chế **Alias (bí danh)**, dịch lệnh `cat` thành lệnh gốc tương đương là `Get-Content`.

## **Phần 2: Hoàn thiện (Bộ lệnh PowerShell)**

* **Xem toàn bộ nội dung tệp (theo luồng):**  
  **Get-Content \-Path "server\_log\_800MB.log" | More**  
* **Xem 10 dòng cuối cùng:**   
  **Get-Content  "server\_log\_800MB.log" \-Tail 10**

