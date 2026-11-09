# Session22_Ex05

## 1. Mục tiêu

Thiết lập quy trình troubleshooting nội bộ để nhóm startup xử lý lỗi môi trường như Docker và xung đột cổng hiệu quả hơn, đồng thời hạn chế câu hỏi trùng lặp trong nhóm chat.

## 2. Vấn đề

Thông tin lỗi hiện được gửi rời rạc trong chat và nhanh chóng bị trôi. Người hỗ trợ thường thiếu bối cảnh, các bước tái hiện và log cần thiết để chẩn đoán.

## 3. Cách làm

### Mẫu Bug Report bắt buộc

Trước khi nhờ hỗ trợ, hãy tạo một bài báo lỗi trong kênh troubleshooting theo mẫu sau:

```markdown
## Tiêu đề
[Môi trường/ứng dụng] Mô tả ngắn lỗi

### Context (Bối cảnh)
- Hệ điều hành và phiên bản:
- Phiên bản Docker/công cụ liên quan:
- Nhánh hoặc commit đang dùng:
- Thao tác ngay trước khi lỗi xảy ra:
- Lỗi bắt đầu từ khi nào? Có thay đổi gì gần đây không?

### Expected (Kết quả mong đợi)
Mô tả điều bạn nghĩ sẽ xảy ra.

### Actual (Kết quả thực tế)
Mô tả điều đã xảy ra và các bước tái hiện lỗi:
1.
2.
3.

### Log (Nhật ký lỗi)
Dán thông báo lỗi và log liên quan vào đây. Che token, mật khẩu, khóa API và dữ liệu nhạy cảm trước khi đăng.

### Đã tự tra cứu
- Từ khóa đã tìm:
- Tài liệu/issue đã kiểm tra:
- Giải pháp đã thử và kết quả:
```

### Quy trình tra cứu 3 bước

1. **Googling:** Tìm cụm lỗi chính xác trong dấu ngoặc kép, kèm tên công cụ và phiên bản, ví dụ: `"port is already allocated" Docker Windows 11`. Ưu tiên tài liệu chính thức và kết quả gần đây.
2. **Community Search:** Tìm trong GitHub Issues, Stack Overflow và lịch sử kênh troubleshooting nội bộ. Kiểm tra ngày đăng, phiên bản, phản hồi xác nhận và tác động của cách sửa; không chạy lệnh nếu chưa hiểu nó thay đổi gì.
3. **AI Translation:** Nếu tài liệu hoặc thảo luận khó hiểu, đưa phần liên quan cùng Context và Log đã loại bỏ thông tin nhạy cảm cho AI để nhờ giải thích bằng ngôn ngữ đơn giản. Yêu cầu AI nêu giả định, phiên bản áp dụng và nguồn tham khảo; tự xác minh hướng dẫn trước khi thực hiện.

Sau ba bước, nếu chưa xử lý được, đăng Bug Report đã điền đủ vào kênh hỗ trợ và liên kết các nguồn đã tra cứu. Người hỗ trợ có thể tìm kiếm tiêu đề hoặc thông báo lỗi trong kênh trước khi mở bài mới, giúp tránh hỏi và xử lý trùng lặp.

**Mục tiêu vận hành:** Theo dõi số lỗi được tự giải quyết sau quy trình để đánh giá mục tiêu xử lý khoảng 80% vấn đề trước khi cần hỗ trợ. Đây là mục tiêu cần đo lường, không phải cam kết rằng mọi lỗi đều tự xử lý được.
