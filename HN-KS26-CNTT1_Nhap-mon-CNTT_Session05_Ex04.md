## **Phần 1: Bảng so sánh Absolute Path và Relative Path**

| Tiêu chí | Đường dẫn tuyệt đối (Absolute Path)C:\\Users\\An-K26\\FarmProject\\data\\logs.csv | Đường dẫn tương đối (Relative Path)../data/logs.csv |
| :---- | :---- | :---- |
| **Độ dài** | Dài, chứa toàn bộ cấu trúc ổ đĩa từ gốc đến file. | Ngắn gọn, chỉ tính từ vị trí script hiện tại. |
| **Tính di động (Portability)** | **Kém.** Dễ hỏng code khi đổi máy, sang hệ điều hành khác (Linux/macOS) hoặc đổi tên user/thư mục gốc. | **Tốt.** Chạy bình thường trên mọi máy/môi trường miễn là giữ nguyên cấu trúc thư mục dự án. |

## **Phần 2: Giải pháp tối ưu & Ý nghĩa ký hiệu**

* **Lựa chọn:** Đường dẫn tương đối (../data/logs.csv) là giải pháp tối ưu.  
* **Ý nghĩa ký hiệu ..:** Dùng để lùi lại (đi ngược lên) một cấp thư mục so với vị trí hiện tại của file script đang chạy, giúp truy cập vào thư mục cha trước khi trỏ tiếp tới data/logs.csv.

