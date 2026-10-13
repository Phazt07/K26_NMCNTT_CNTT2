## **Phần 1: Lỗi ở đâu?**

`-CaseSensitive` làm lệnh phân biệt chữ hoa và chữ thường. Pattern là `"critical"` nhưng log ghi `"CRITICAL"`, nên không dòng nào được tìm thấy.

File vẫn có 2 dòng tiêu đề, rồi script đếm được 2 dòng đó. Số 2 không phải số lỗi.

## **Phần 2: Sửa script**

Bỏ `-CaseSensitive` và đếm số dòng tìm được:

\$errors \= Select-String \-Path server.log \-Pattern "critical"

"=== Bat dau quet log: \$(Get-Date) \===" | Out-File daily\_critical.txt  
\$errors | Out-File \-Append daily\_critical.txt  
"=== Hoan tat. So dong loi: \===" | Out-File \-Append daily\_critical.txt  
\$errors.Count | Out-File \-Append daily\_critical.txt

Kết quả có hai dòng lỗi CRITICAL và số lượng là `2`.

Nếu không có `server.log`, PowerShell sẽ báo lỗi ở lệnh `Select-String`. Thường script vẫn chạy tiếp và ghi các dòng tiêu đề vào file kết quả.

