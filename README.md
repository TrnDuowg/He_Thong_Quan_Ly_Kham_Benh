# HỆ THỐNG QUẢN LÝ KHÁM BỆNH ĐA KHOA

**Bài tập Lớn môn Cấu trúc Dữ liệu và Giải thuật - Đại học Bách Khoa Hà Nội**

---

## 1. Thông tin nhóm sinh viên

| STT | Họ và tên | Mã sinh viên |
|:---:|---|:---:|
| 1 | **Phạm Ngọc Đức Anh** | 20237294 |
| 2 | **Trần Công Dương** | 20237321 |
| 3 | **Nguyễn Thị Minh Hằng** | 20237324 |

---

## 2. Cấu trúc mã nguồn

Dự án được tổ chức theo các mô-đun chức năng riêng biệt:

- `main_gui.py`: Chứa mã nguồn cho giao diện người dùng đồ họa (GUI), sử dụng thư viện **CustomTkinter**. Đây là điểm khởi chạy chính của chương trình.
- `app_logic.py`: Chứa logic nghiệp vụ cốt lõi, đóng vai trò điều phối giữa giao diện (GUI) và các lớp dữ liệu.
- `models.py`: Định nghĩa các lớp đối tượng (Object Class) đại diện cho thực thể trong hệ thống:
  - `Patient` (Bệnh nhân)
  - `Doctor` (Bác sĩ)
  - `Clinic` (Phòng khám)
  - `PatientInQueue` (Đối tượng trong hàng đợi)
- `custom_structures.py`: **[QUAN TRỌNG]** Chứa cài đặt thủ công các Cấu trúc dữ liệu & Giải thuật phục vụ yêu cầu môn học:
  - `LinkedList` (Danh sách liên kết)
  - `HashTable` (Bảng băm)
  - `MaxHeap` (Đống cực đại)
  - `PriorityQueue` (Hàng đợi ưu tiên)
  - `RadixTree` (Cây cơ số - dùng cho tìm kiếm nhanh)
- `requirements.txt`: Danh sách các thư viện Python cần thiết.
- `*.csv` (`patients_data.csv`, ...): Cơ sở dữ liệu lưu trữ dưới dạng file văn bản.

---

## 3. Mô tả chức năng

Chương trình mô phỏng quy trình khám bệnh thực tế tại cơ sở y tế với các chức năng:

###  Quản lý Hệ thống
- **Quản lý Bác sĩ**: Thêm, sửa, xóa thông tin bác sĩ.
- **Quản lý Phòng khám**: Thiết lập phòng khám và phân công bác sĩ trực thuộc.

###  Quản lý Bệnh nhân & Hồ sơ
- **Thao tác cơ bản**: Thêm mới, cập nhật, xóa hồ sơ bệnh nhân.
- **Tìm kiếm nâng cao**: Ứng dụng **Radix Tree** để tìm kiếm tức thì (Instant Search) theo Số điện thoại hoặc CCCD.
- **Lịch sử**: Lưu trữ chi tiết lịch sử khám bệnh.

###  Quy trình Khám bệnh (Core Feature)
- **Đăng ký khám**: Đưa bệnh nhân vào hàng đợi với các mức độ ưu tiên khác nhau (Ưu tiên cao/Thường).
- **Quản lý Hàng đợi (Priority Queue)**:
  - Tự động sắp xếp bệnh nhân dựa trên độ ưu tiên và thời gian đến.
  - Các thao tác: Gọi bệnh nhân kế tiếp, Xử lý vắng mặt (bỏ qua), Hủy đăng ký, Thay đổi độ ưu tiên.
- **Hoàn thành khám**: Ghi nhận chẩn đoán và lưu vào lịch sử.

---

## 4. Cài đặt và Chạy chương trình

**Yêu cầu:** Python 3.x đã được cài đặt.

1. Cài đặt các thư viện cần thiết:
   ```bash
   pip install -r requirements.txt
