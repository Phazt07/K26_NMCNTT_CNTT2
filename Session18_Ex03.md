### **1\. Vấn đề**

* **Tình huống:** Giao diện "Theo dõi lộ trình xe" trên web bị vỡ, khung "Thông tin tài xế" đè lên khung "Danh sách trạm" do kích thước và khoảng cách lộn xộn.  
* **Nguyên nhân:** Các thông số khoảng cách (Box Model) giữa các phần tử đang bị cấu hình sai, dẫn đến xung đột không gian hiển thị.


### **2\. Yêu cầu**

* **Định vị lỗi:** Sử dụng tính năng Inspect Element để tìm chính xác thẻ HTML bị lỗi trong cây DOM Tree.  
* **Tối ưu Layout:** Phân tích 4 lớp của CSS Box Model (Content, Padding, Border, Margin) để tách biệt hai khung nội dung.  
* **Ràng buộc:** Không sửa file mã nguồn gốc, chỉ đề xuất thay đổi thông qua tab Styles trong DevTools.

### **3\. Cách làm**

#### **Phần 1\. Phân tích**

* Truy cập tab **Computed** trong DevTools để quan sát sơ đồ 4 lớp của phần tử lỗi:  
  * **Content:** Kích thước nội dung bên trong.  
  * **Padding:** Khoảng cách từ nội dung đến viền.  
  * **Border:** Đường viền của phần tử.  
  * **Margin:** Khoảng cách giữa các phần tử  
    

#### **Phần 2\. Triển khai**

* Thao tác trực tiếp trên tab **Styles** của DevTools.  
* Điều chỉnh lại các thông số khoảng cách tăng margin-bottom hoặc margin-top (vd:50px) để tách biệt hoàn toàn hai khung nội dung, loại bỏ hiện tượng chồng lấn.


#### **Phần 3\. Kiểm thử**

* **Tình huống:** Đã thay đổi thông số Margin nhưng phần tử vẫn đứng yên không di chuyển.  
* **Cách khắc phục:**  
  * Kiểm tra tab **Styles** xem có thuộc tính nào có độ ưu tiên cao hơn (hoặc dùng \!important) đang ghi đè ở tầng Browser Engine hay không.  
  * Kiểm tra xem phần tử có đang bị kẹt trong thuộc tính định vị (position: absolute hoặc fixed) khiến margin không tác dụng theo ý muốn hay không.

