# 🛡️ Dự án Nhận diện và Phân loại Tình trạng Đeo Khẩu Trang với YOLOv8n

## 🧠 Mục tiêu
Phân loại hình ảnh khuôn mặt thành **6 lớp** dựa trên tình trạng đeo khẩu trang bằng mô hình YOLOv8n:
- `incorrect_mc` – Đeo khẩu trang dưới cằm
- `incorrect_mmc` – Đeo khẩu trang che miệng nhưng không che mũi
- `mask_simple` – Khẩu trang đơn giản
- `mask_complex` – Khẩu trang có hoa văn
- `no_mask_simple` – Không đeo khẩu trang (mặt trống)
- `no_mask_complex` – Không khẩu trang (có râu, tóc, vật cản...)

---

## 👥 Thành viên thực hiện
1. **Võ Hoài Sơn**
2. **Nguyễn Trọng Nhân**

---

## 📁 Cấu trúc file trong GitHub
| Tên file             | Mô tả |
|----------------------|-------|
| `training.ipynb`     | Notebook huấn luyện mô hình phân loại 6 lớp sử dụng YOLOv8n. Bao gồm các bước xử lý ảnh, chia dữ liệu, huấn luyện và đánh giá mô hình. |
| `inference.ipynb`    | Notebook thực hiện nhận diện khuôn mặt thời gian thực từ webcam/video, phân loại lớp khẩu trang, hiển thị kết quả và FPS. |
| `best.pt`            | File trọng số mô hình tốt nhất đã được huấn luyện từ YOLOv8n-classification. |

---

## 📚 Dataset
Dữ liệu được sử dụng từ Kaggle:  
📎 [Face Mask Dataset – FMD_DATASET](https://www.kaggle.com/datasets/shiekhburhan/face-mask-dataset)

Các ảnh được xử lý qua MediaPipe để crop khuôn mặt, offset vùng mặt rộng hơn 1.2 lần, chuyển sang grayscale rồi nhân lên RGB 3 kênh để huấn luyện.

---

## 🧪 Huấn luyện
Mô hình được huấn luyện trên nền tảng Kaggle với GPU T4 x2.  
📎 **Đường dẫn đến Notebook Kaggle:** [*Kaggle Project*](https://www.kaggle.com/code/vohoaison/face-mask-detection)

Kết quả huấn luyện:
- Accuracy đạt được trên tập test: *(cập nhật sau khi train)*
- Mô hình có khoảng **3.4 BFLOPs** (đạt yêu cầu < 7 BFLOPs)

---

## 🎥 Demo
📎 **Link video demo trên YouTube:** [*Youtube Demo Video*](https://youtu.be/bsN138Of28w)

Nội dung video:
- Hiển thị real-time video webcam
- Nhận diện khuôn mặt bằng MediaPipe
- Phân loại lớp khẩu trang và vẽ nhãn trên từng người
- Hiển thị FPS thời gian thực

