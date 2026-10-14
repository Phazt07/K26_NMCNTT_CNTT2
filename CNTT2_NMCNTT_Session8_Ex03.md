Phần 1: Phân tích luồng dữ liệu (Pipeline) 

\[Get-Content access.log\]   
       │ (Truyền Object dòng văn bản)  
       v  
\[Select-String "TIMEOUT"\]   
       │ (Lọc và loại bỏ dòng chứa NOT TIMEOUT)  
       v  
\[Where-Object { \$\_.Line \-notmatch "NOT TIMEOUT" }\]  
       │ (Đếm số lượng đối tượng kết quả hợp lệ)  
       v  
\[Thuộc tính .Count\] ➔ Trả về con số tổng duy nhất

Phần 2: Triển khai câu lệnh PowerShell 

(Get-Content access.log | Select-String "TIMEOUT" | Where-Object { \$\_.Line \-notmatch "NOT TIMEOUT" }).Count