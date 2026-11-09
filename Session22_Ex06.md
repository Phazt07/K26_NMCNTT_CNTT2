# Session22_Ex06

## 1. Mục tiêu

Kết hợp prompt AI và Bug Reporting để xử lý lỗi quyền truy cập khi đẩy code lên GitHub.

## 2. Vấn đề

Khi chạy Git, Terminal báo:

```text
error: open(".git/FETCH_HEAD"): Permission denied
```

Chạy lại lệnh nhưng lỗi vẫn còn.

## 3. Cách làm

### Prompt AI theo công thức 3 thành phần

**Bối cảnh + Nhiệm vụ + Yêu cầu đầu ra**

> Tôi đang dùng Git trên **[Windows/macOS/Linux và phiên bản]**. Khi **[ghi lệnh Git vừa chạy]**, Terminal báo `error: open(".git/FETCH_HEAD"): Permission denied`. Tôi đã thử chạy lại nhưng vẫn gặp lỗi. Hãy giải thích nguyên nhân có thể xảy ra bằng ngôn ngữ thật đơn giản, hướng dẫn kiểm tra từng bước và nêu rõ tác động của mỗi lệnh trước khi đề xuất. Không giả định rằng cần quyền Administrator; hãy ưu tiên cách ít rủi ro và phù hợp với hệ điều hành của tôi. Nếu thiếu thông tin, hãy hỏi tôi. Dẫn tài liệu chính thức để tôi kiểm chứng.

### Nếu AI đề xuất chạy với quyền Administrator

Trên Windows, chỉ thử cách này nếu lệnh và tác động đã được kiểm tra, và bạn có quyền quản trị máy:

1. Đóng các Terminal đang thao tác trên repository.
2. Mở **Windows Terminal** hoặc **PowerShell** bằng cách chọn **Run as administrator**.
3. Chuyển đến đúng thư mục repository, kiểm tra đường dẫn, rồi chạy lại đúng lệnh Git đã gây lỗi.
4. Nếu vẫn thất bại, dừng lại và ghi nhận kết quả. Không tiếp tục thay đổi quyền hàng loạt hoặc xóa tệp trong `.git` khi chưa hiểu rõ nguyên nhân.

Quyền Administrator chỉ tăng quyền của tiến trình; nó không nhất thiết khắc phục nguyên nhân và có thể tạo tệp Git do Administrator sở hữu, gây lỗi quyền về sau. Vì vậy, nếu mở Terminal nâng quyền cũng không giải quyết được, hãy đóng Terminal đó và nhờ giảng viên kiểm tra quyền sở hữu/quyền truy cập thư mục repository.

### Ảnh chụp minh họa

Môi trường này không có cửa sổ Terminal thực tế của người học để thao tác hoặc chụp ảnh lỗi. Khi tự thực hiện, hãy chụp ảnh màn hình Terminal sau khi chạy lại lệnh và gặp lỗi (hoặc kết quả đã xử lý), rồi:

- Cắt ảnh gọn quanh lệnh và dòng lỗi; khoanh vùng dòng `Permission denied` bằng viền hoặc mũi tên.
- Giữ lại đủ ngữ cảnh để thấy lệnh vừa chạy, nhưng không để lộ thông tin không cần thiết.
- Che tên tài khoản, đường dẫn có tên cá nhân, email, token, khóa truy cập và nội dung riêng tư trước khi gửi.
- Không chỉnh sửa nội dung lỗi theo cách làm sai lệch bằng chứng.

### Tin nhắn nhờ giảng viên theo Bug Reporting Framework

> **Tiêu đề:** Git không thể đọc `.git/FETCH_HEAD` — Permission denied
>
> **Context (Bối cảnh):** Em đang dùng **[hệ điều hành/phiên bản]**, Git **[phiên bản]**. Repository ở **[đường dẫn đã che thông tin cá nhân]**. Lỗi xuất hiện khi em chạy lệnh **[lệnh Git]** để đẩy code lên GitHub.
>
> **Expected (Mong đợi):** Git hoàn tất thao tác và đẩy code lên GitHub.
>
> **Actual (Thực tế):** Terminal báo `error: open(".git/FETCH_HEAD"): Permission denied`. Em đã thử chạy lại **[số lần/chi tiết]**. Sau đó em đã thử **[các bước đã thực hiện, gồm có/không thử Run as administrator]**, kết quả là **[kết quả]**.
>
> **Log (Nhật ký):** **[dán toàn bộ thông báo lỗi liên quan hoặc đính kèm ảnh đã che thông tin nhạy cảm]**.
>
> **Nhờ hỗ trợ:** Thầy/cô giúp em kiểm tra quyền truy cập hoặc quyền sở hữu của thư mục `.git` và hướng dẫn cách sửa an toàn được không ạ? Em chưa tự ý thay đổi quyền hàng loạt hay xóa dữ liệu trong repository.
