##  **\# Smart-Farm (Trang trại Lan)**

## 

## **\*Hệ thống quản lý và tưới cây tự động tích hợp IoT.\***

## 

## **\#\# Hướng dẫn cài đặt**

## **\`\`\`bash**

## **git clone \[https\://github.com/username/smart-farm.git\](https\://github.com/username/smart-farm.git)**

## **cd smart-farm**

## **npm install**

## 

## **Tính năng**

* \[x\] Tự động đo độ ẩm đất  
*   
* \[ \] Điều khiển tưới từ xa  
*   
* \[ \] Cảnh báo nhiệt độ  
* 

##  **Bảng thông số**

| Thiết bị | Thông số | Trạng thái |
| :---- | :---- | :---- |
| Cảm biến độ ẩm | 0 \- 100% | Hoạt động |
| Máy bơm mini | 12V | Sẵn sàng |

**Chu kỳ CPU:** Fetch (Lấy lệnh tưới) ➔ Decode (Giải mã lệnh) ➔ Execute (Bật rơ-le bơm nước).

##  **Mô hình DIKW**

1. **Data:** Nhiệt độ 35°C.  
2. **Information:** Trời nóng, đất khô hạn.  
3. **Knowledge:** Lan cần được tưới nước ngay.  
4. **Wisdom:** Tự động kích hoạt hệ thống tưới.

