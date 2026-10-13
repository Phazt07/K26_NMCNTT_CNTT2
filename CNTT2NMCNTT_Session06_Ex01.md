Phần 1:

Trong PowerShell, cat là tên viết tắt của Get-Content nên lệnh này in hết file ra màn hình. File 500MB có nhiều dữ liệu nên Terminal hoặc Notepad có thể bị chậm, treo máy.

Phần 2:

Xem file theo từng trang:

Get-Content server\_log\_500MB.log | more

Xem 10 dòng cuối:

Get-Content server\_log\_500MB.log \-Tail 10\`\`\`