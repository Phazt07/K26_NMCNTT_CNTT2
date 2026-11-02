* **Vấn đề:** Khung *"Nội dung bài học"* bị đè lên khung *"Danh sách video"* trên giao diện do lỗi bố cục CSS Box Model hoặc tính toán hình học.  
    
* **Yêu cầu:** Sử dụng tab *Computed* trong DevTools (F12) để phân tích 4 lớp của Box Model (Content, Padding, Border, Margin) và đề xuất thông số chỉnh sửa tại bảng *Styles* nhằm tách biệt hai khung mà không làm vỡ giao diện.  
    
* **Cách làm:**  
  1. Nhấn F12 hoặc chuột phải chọn **Inspect** vào phần tử đang bị chồng lấn.  
  2. Chuyển sang tab **Computed** để quan sát trực quan kích thước và 4 lớp (Content, Padding, Border, Margin).  
  3. Kiểm tra tab **Styles** bên cạnh để tìm các thuộc tính định khoảng cách (margin, padding, height, hoặc position).  
  4. Thử nghiệm thay đổi giá trị trực tiếp trên DevTools (ví dụ: điều chỉnh margin-bottom hoặc top/bottom) cho đến khi hai khung tách rời hợp lý.  
  5. Đưa kết quả phân tích sơ đồ Box Model và thông số giải pháp hoàn chỉnh lên kho lưu trữ GitHub theo đúng định dạng tên yêu cầu của bài tập.

