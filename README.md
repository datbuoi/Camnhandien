# Hướng dẫn sử dụng Hệ thống Camnhandien

Dưới đây là các bước để cài đặt môi trường và sử dụng hai phần của hệ thống: **Nhận diện biển số (Core)** và **Ứng dụng quản lý bãi xe (GUI)**.

---

## 🛠 1. Chuẩn bị môi trường (Bắt buộc)

Trước khi chạy bất kỳ phần nào, bạn cần thực hiện các bước sau:

1. **Di chuyển vào thư mục dự án**:
   ```bash
   cd Camnhandien
   ```

2. **Thiết lập môi trường ảo (venv)**:
   ```bash
   python -m venv venv
   ```

3. **Kích hoạt môi trường ảo**:
   ```bash
   .\venv\Scripts\activate
   ```

4. **Cài đặt thư viện**:
   ```bash
   pip install opencv-python easyocr imutils numpy Pillow
   ```

---

## 📸 PHẦN 1: Chạy Nhận diện & Xử lý Ảnh (main.py)

Phần này dùng để kiểm tra khả năng nhận diện biển số từ ảnh, cắt biển số và lưu dữ liệu thô vào CSV.

**Để khởi chạy:**
```bash
python main.py
```

- **Chức năng**: Quét các ảnh trong thư mục, phát hiện vùng chứa biển số, dùng EasyOCR để đọc chữ và lưu kết quả vào file CSV.
- **Dữ liệu đầu ra**: Các ảnh biển số đã cắt được lưu trong thư mục `plates/`.

---

## 🚗 PHẦN 2: Chạy Ứng dụng Quản lý Bãi xe (parking_app.py)

Đây là ứng dụng đầy đủ với giao diện người dùng, quản lý tài khoản, ví điện tử và lịch sử gửi xe.

**Để khởi chạy:**
```bash
python parking_app.py
```

### Các tính năng chính:
- **Trang chủ**: Thực hiện Quét xe vào (IN) và Xe ra (OUT). Tích hợp trừ tiền tự động từ ví.
- **Tra cứu**: Nhập biển số để xem lịch sử hành trình. Hỗ trợ tính năng **Lướt (Swipe)** bảng để xem chi tiết ghi chú số dư.
- **Tài khoản**: Đăng ký/Đăng nhập để liên kết biển số xe và quản lý số dư ví.

### Cấu trúc dữ liệu liên quan:
- `parking_data.json`: Lưu thông tin tài khoản, ví và lịch sử.
- `parking_sessions/`: Lưu ảnh xe lúc vào/ra để đối chiếu.

---
*Lưu ý: Nếu lệnh `python` không hoạt động, hãy thử thay bằng `py`.*
