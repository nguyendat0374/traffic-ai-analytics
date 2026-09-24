# traffic-ai-analytics
# Traffic AI Analytics - Hệ Thống Phân Tích Giao Thông Thông Minh

Đồ án ứng dụng Trí tuệ Nhân tạo (Computer Vision & Deep Learning) trong việc nhận diện, theo dõi và phân tích lưu lượng phương tiện giao thông từ camera quan sát.

---

## 📌 1. Mục Tiêu Đề Tài
- **Phát hiện & Phân loại phương tiện:** Nhận diện chính xác các loại phương tiện tham gia giao thông (ô tô, xe máy, xe buýt, xe tải,...) bằng mô hình thị giác máy tính tiên tiến (YOLOv8/YOLOv11).
- **Theo dõi & Đếm lưu lượng:** Ứng dụng các thuật toán tracking (ByteTrack/BoT-SORT) để giám sát luồng di chuyển và thống kê mật độ phương tiện theo thời gian thực.
- **Tối ưu hóa huấn luyện:** Triển khai huấn luyện và thực nghiệm trên môi trường đám mây Google Colab (GPU Tesla T4), đồng bộ dữ liệu với Google Drive.

---
## 📁 2. Cấu Trúc Thư Mục Dự Án

### 2.1. Cấu trúc mã nguồn trên GitHub
```text
traffic-ai-analytics/
├── configs/               # File cấu hình tham số (detector.yaml, tracker.yaml)
├── src/                   # Mã nguồn chính của dự án
│   ├── analytics/         # Phân tích luồng (counting.py, violation.py)
│   ├── utils/             # Các hàm bổ trợ và tiện ích
│   ├── __init__.py
│   ├── detector.py        # Module phát hiện đối tượng
│   └── tracker.py         # Module theo dõi phương tiện (tracking)
├── notebooks/             # Chứa các file Jupyter/Colab notebook
├── .gitignore             # Danh sách file/thư mục không đưa lên Git
├── LICENSE                # Giấy phép mã nguồn mở
├── main.py                # Điểm khởi chạy pipeline chính
├── requirements.txt       # Danh sách thư viện và dependencies cần cài đặt
└── README.md              # Tài liệu mô tả và hướng dẫn dự án
```
