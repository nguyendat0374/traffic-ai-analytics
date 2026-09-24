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
### 2.2. Cấu trúc lưu trữ dữ liệu trên Google Drive (`TRAFFIC_AI_PROJECT/`)
```text
TRAFFIC_AI_PROJECT/
├── 01_Docs/               # Tài liệu nghiên cứu, bài báo và báo cáo đồ án
├── 02_Data/
│   ├── Raw_Data/          # Video và hình ảnh gốc thu thập được
│   └── Processed_Data/    # Dữ liệu sau khi trích xuất frame, gán nhãn
└── 03_Models_Code/        # Lưu trữ checkpoint trọng số (.pt) và code phụ trợ
```
---

## 🏷️ 3. Quy Tắc Đặt Tên (Naming Conventions)

| Đối tượng | Định dạng đặt tên | Ví dụ cụ thể | Ghi chú quản lý |
| :--- | :--- | :--- | :--- |
| **Model Trọng số** | `[Model]_[Dataset]_[Mã_Thí_nghiệm]_[Trạng_thái].pt` | `yolov8n_trafficv1_exp01_best.pt`<br>`yolov8s_trafficv2_exp02_last.pt` | Bổ sung mã dataset và thí nghiệm. **Quy tắc: Không ghi đè trọng số**. |
| **Video Dữ liệu** | `VID_[Địa_điểm]_[Khung_giờ]_[Ngày].mp4` | `VID_NgaTuSo_08h_20260920.mp4` | Ghi rõ địa điểm, khung giờ và ngày quay. |
| **Notebook** | `[Mã_tuần]_[Nội_dung_công_việc].ipynb` | `W01_Colab_Setup_Test.ipynb`<br>`W02_Data_Preprocessing.ipynb` | Đánh số theo tuần tiến độ đồ án. |
| **Mã nguồn** | `[tên_chức_năng].py` *(chữ thường, gạch dưới)* | `detector.py`, `tracker.py` | Tuân thủ chuẩn PEP8. |

---
## 🚀 4. Hướng Dẫn Cài Đặt & Chạy Dự Án

### Cài đặt môi trường
```bash
git clone [https://github.com/nguyendat0374/traffic-ai-analytics.git](https://github.com/nguyendat0374/traffic-ai-analytics.git)
cd traffic-ai-analytics
pip install -r requirements.txt
```
