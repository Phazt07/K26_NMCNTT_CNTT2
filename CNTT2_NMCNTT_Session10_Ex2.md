# Hướng dẫn cài đặt cảm biến độ ẩm

Để cài đặt biến môi trường, sử dụng lệnh `export HUMIDITY_SENSOR=1`.

## Code điều khiển máy bơm
```python
import time

def pump_control(moisture):
    if moisture < 30:
        print("Bật máy bơm nước cho vườn Lan!")
    else:
        print("Độ ẩm ổn định.")
Tiêu chí          Loại cũ         Loại mới
Độ chính xác      Thấp            Cao
Giá thành         Rẻ              Tầm trung
Task List kiểm tra thiết bị
[x] Kết nối cảm biến với vi điều khiển

[ ] Kiểm tra nguồn điện 5V

[ ] Chạy thử script Python