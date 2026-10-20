# BÀI LÀM – ÔN TẬP NGÀY 1

- **Họ tên:** Lã Đức Phát
- **Lớp:** CNTT2
- **Link repository:https://github.com/Phazt07/K26_NMCNTT_CNTT2.git**
- **Hệ điều hành (Windows/macOS):** Windows

## Phần A. Tổ chức thư mục bằng GUI

> Phần A được chấm qua kết quả B1 (tên thư mục gốc) và kết quả liệt kê toàn bộ dự án B8 ở Phần B, không cần ghi thêm ở đây.

## Phần B. Thao tác bằng CLI

### Các lệnh đã chạy (B1–B7)

```shell
pwd
ls -Force
mv lich_hoc.txt docs/
mv logo_trung_tam.png media/
mv anh_lop_hoc.jpg media/
cp media/logo_trung_tam.png archive/
rm temp_201.tmp
rm temp_202.tmp
cd logs
ls
cd ..
cd docs
cp ../media/anh_lop_hoc.jpg ../archive/
cd ..
```

### Kết quả B1 (pwd)

```text
Path
----
C:\Users\lapha\Documents\Codex\2026-10-20\s\outputs\trung-tam-tieng-anh
```

### Kết quả liệt kê toàn bộ dự án – B8 (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
archive\
data\
docs\
logs\
media\
.env
bai_lam_ngay1.md
archive\anh_lop_hoc.jpg
archive\logo_trung_tam.png
data\hoc_vien_khoa_3.xlsx
docs\lich_hoc.txt
logs\access.log
media\anh_lop_hoc.jpg
media\logo_trung_tam.png
```

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
