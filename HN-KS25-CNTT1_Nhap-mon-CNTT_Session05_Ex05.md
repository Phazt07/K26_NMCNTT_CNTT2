Bài 5 

1. Sơ đồ luồng 

| IPO | Chi tiết |
| :---- | :---- |
| Input | Các folder chứa các file ảnh và file code |
| Process | Tiến hành gom các file ảnh vào trong folder media, các file code vào trong  folder scripts |
| Output | Các file ảnh, file code được đưa vào đúng folder |

     2\. Danh sách các câu lệnh cho robot

1. đưa về folder Download : cd \~/Download  
2. tạo 2 folder : media và scripts : mkdir media, scripts  
3. gom các file ảnh có đuôi (.jpg, .png) đưa vào folder media  
   mv \* .jpg, \*.png media  
4. gom các file code có đuôi (.py) đưa vào folder scripts  
   mv \*.py scripts/   
5. rm \*.tmp 

