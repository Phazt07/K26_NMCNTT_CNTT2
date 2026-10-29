## **Phần 1: Phân tích bài toán (I/O)**

**Đầu vào**

* Tài liệu thuộc 5 loại: mã nguồn và tài liệu kỹ thuật; thiết kế và tài sản đồ họa; Business Plan và tài liệu đối tác; slide pitch và business summary dùng chung; tài liệu nhạy cảm như API keys và thông tin khách hàng.  
* Người dùng thuộc 4 vai trò: Ban Kỹ thuật (3), Ban Thiết kế (2), Ban Kinh doanh (2), nhà đầu tư bên ngoài (1).

**Đầu ra mong đợi**

* Cấu trúc Google Drive hai cấp: thư mục dự án, bên trong là thư mục theo ban và thư mục cộng tác.  
* Bảng phân quyền theo vai trò và loại tài liệu, với quyền chỉ xem, nhận xét hoặc chỉnh sửa được cấp theo nhu cầu công việc.

### **Cấu trúc thư mục đề xuất**

```
CampusPay/
├── 01_KyThuat/
├── 02_ThietKe/
├── 03_KinhDoanh/
├── 04_CongTac_Chung/
└── 05_NhayCam_Restricted/
```

* `01_KyThuat`: mã nguồn, tài liệu API, kết quả kiểm thử; **không lưu API keys** trực tiếp trong Drive.  
* `02_ThietKe`: file UI, tài sản đồ họa và tài liệu thiết kế.  
* `03_KinhDoanh`: Business Plan, nghiên cứu thị trường và tài liệu đối tác.  
* `04_CongTac_Chung`: slide pitch và business summary; chọn một nhóm làm chủ nội dung, các nhóm khác chỉ nhận xét hoặc xem.  
* `05_NhayCam_Restricted`: thông tin khách hàng, thông tin xác thực và tài liệu nhạy cảm cần giới hạn người truy cập. Nếu lưu khóa bí mật, nên dùng secret manager phù hợp; thư mục Drive không thay thế kho quản lý bí mật.

Cấp quyền ở từng thư mục theo nhóm người dùng cần truy cập. Riêng file cần quyền chặt hơn thư mục cha, đặt trong thư mục giới hạn quyền hoặc chia sẻ riêng để quyền kế thừa không mở rộng ngoài ý muốn. Drive áp dụng quyền thư mục cho nội dung bên trong; người có quyền Editor ở thư mục không thể bị hạ xuống Viewer chỉ trên một file con. [Google Drive Help](https://support.google.com/drive/answer/7166529?hl=en)

### **Các bước cấu hình từ đầu**

1. Tạo thư mục dự án và năm thư mục con như trên; đặt tên nhất quán, chỉ định người quản lý quyền.  
2. Chuyển tài liệu vào đúng thư mục; đánh dấu tài liệu mật và rà soát file có dữ liệu nhạy cảm.  
3. Cấp quyền cho từng nhóm theo bảng dưới, ưu tiên nhóm/email công việc; dùng chia sẻ cho người cụ thể, không dùng “Anyone with the link”.  
4. Chia sẻ Business Plan cho Ban Kỹ thuật dưới quyền **Viewer**; chia sẻ PDF pitch cho nhà đầu tư dưới quyền **Viewer**, đặt ngày hết hạn 14 ngày.  
5. Kiểm tra bằng tài khoản thuộc từng vai trò: chỉ thấy đúng thư mục/file cần thiết, không sửa được tài liệu ngoài phạm vi.  
6. Bật quản lý phiên bản cho tài liệu quan trọng và xác nhận thời gian lưu phù hợp với chính sách tài khoản; Drive Version History không đồng nghĩa mọi loại file đều được đảm bảo giữ tối thiểu 30 ngày.  
7. Khi đổi nhiệm vụ hoặc nhân sự nghỉ việc, thu hồi quyền trực tiếp và quyền qua nhóm, rồi kiểm tra lại quyền kế thừa và các liên kết chia sẻ.

## **Phần 2: Triển khai & chống lỗi**

### **Bảng phân quyền**

| Loại tài liệu | Ban KT | Ban TK | Ban KD | Nhà đầu tư | Ghi chú bảo mật |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Mã nguồn, tài liệu API, kiểm thử | **Editor** | Không truy cập | Không truy cập | Không truy cập | Lưu mã nguồn trong hệ thống quản lý mã nguồn; không để khóa API trong Drive |
| Thiết kế UI, tài sản đồ họa | **Viewer** | **Editor** | Không truy cập | Không truy cập | Chỉ chia sẻ chéo khi công việc yêu cầu |
| Business Plan, nghiên cứu và tài liệu đối tác | **Viewer** | Không truy cập | **Editor** | Không truy cập | Tài liệu mật; Ban KT chỉ xem để hiểu bối cảnh |
| Slide pitch, business summary | **Commenter** | **Commenter** | **Editor** | **Viewer** | Ban KD quản lý nội dung; nhà đầu tư truy cập file PDF riêng hoặc bản xuất phù hợp |
| Thông tin khách hàng, API keys và dữ liệu nhạy cảm | Không truy cập mặc định | Không truy cập mặc định | Chỉ người được chỉ định, tối thiểu cần thiết | Không truy cập | Restricted, không chia sẻ bằng link công khai; ưu tiên secret manager cho API keys |

*Editor/Viewer ở hàng tài liệu nhạy cảm chỉ cấp cho cá nhân được chỉ định khi thực sự cần; không cấp mặc định cho cả ban.*

### **Ba bẫy dữ liệu**

1. **Ban Kỹ thuật cần đọc Business Plan nhưng không được sửa:** cấp **Viewer** trên Business Plan. Viewer cho phép xem mà không cho chỉnh sửa. Nếu cần phản hồi, có thể cấp **Commenter** khi chủ tài liệu chấp thuận, nhưng quyền tối thiểu đúng với yêu cầu hiện tại là Viewer. [Google Drive Help](https://support.google.com/drive/answer/2494822?hl=f)  
2. **Nhà đầu tư cần tải PDF pitch để trình bày offline, không được sửa:** chia sẻ **bản PDF** với quyền **Viewer** và đặt ngày hết hạn sau 14 ngày. Không cần tắt “Viewers can download” nếu cần họ tải bản PDF; Viewer vẫn không có quyền sửa file. Nếu PDF hoặc thư mục có nội dung không nên sao chép, có thể tắt tải xuống/in/sao chép, nhưng khi đó nhà đầu tư không tải được bản offline. Việc hạn chế tải xuống cũng không thể thu hồi bản PDF sau khi người nhận đã tải. [Google Drive Help](https://support.google.com/drive/answer/7166529?hl=en)  
3. **Thành viên nghỉ việc:** thu hồi quyền truy cập ngay tại tài khoản hoặc nhóm quản trị danh tính của tổ chức: vô hiệu hóa tài khoản/phiên đăng nhập theo quy trình quản trị, gỡ người đó khỏi các nhóm được cấp quyền, thu hồi chia sẻ trực tiếp và rà soát quyền sở hữu/tệp họ quản lý. Chỉ xóa quyền ở một thư mục có thể chưa đủ nếu người đó còn quyền qua nhóm, chia sẻ trực tiếp hoặc thư mục khác.

**Lưu ý về hạn 14 ngày và Version History:** đặt expiration trực tiếp trên file investor được chia sẻ, nếu tài khoản Workspace hỗ trợ. Nếu chia sẻ cả thư mục, expiration của thư mục chỉ hỗ trợ vai trò Viewer trên tài khoản đủ điều kiện; hãy kiểm tra xem nhà đầu tư có quyền kế thừa ở thư mục cha hay không, vì hết hạn quyền file có thể chỉ đưa quyền về mức của thư mục cha. [Google Workspace Learning Center](https://support.google.com/a/users/answer/13005112?rd=1) Để đảm bảo yêu cầu lưu lịch sử tối thiểu 30 ngày, quản trị viên cần xác nhận cấu hình và chính sách lưu giữ của Workspace; không nên xem Version History mặc định là cam kết lưu mọi phiên bản trong 30 ngày.

