# Hướng dẫn chạy Notebook

Notebook này thực hiện một số xử lý liên quan đến ảnh và mô hình học sâu. Để chạy được notebook, bạn cần cài đặt các thư viện cần thiết và sử dụng Jupyter Notebook hoặc Google Colab.

## Cài đặt thư viện

Chạy đoạn lệnh sau để cài đặt các thư viện cần thiết:

```bash
pip install numpy opencv-python matplotlib tensorflow
```

```hoặc trực tiếp từ Jupyter Notebook 
!pip install opencv-python numpy matplotlib tensorflow
```

## Hướng dẫn chạy

1. Mở Jupyter Notebook hoặc Google Colab.
2. Tải notebook `.ipynb` lên.
3. Chạy tuần tự từng cell để thực hiện xử lý.

## Thư viện sử dụng

- `numpy`: xử lý mảng số liệu
- `opencv-python`: đọc và xử lý ảnh
- `matplotlib`: hiển thị ảnh
- `tensorflow`: sử dụng cho mô hình học sâu nếu có


👤 Nhận Diện Khuôn Mặt bằng Haar Cascade (OpenCV)

📌 Giới thiệu
Chương trình Python sử dụng thuật toán Haar Cascade từ thư viện OpenCV để nhận diện khuôn mặt người trong ảnh hoặc webcam theo thời gian thực. Giao diện đơn giản, dễ sử dụng qua dòng lệnh.

🧠 Chức năng chính
- Chương trình cho phép nhận diện khuôn mặt bằng thuật toán Haar Cascade trong thư viện OpenCV với 2 chế độ:

1. 🎥 Nhận diện từ Webcam
Mở webcam của máy tính.
- Quét liên tục các khung hình.
- Phát hiện và vẽ khung đỏ quanh khuôn mặt.
- Hiển thị nhãn "Face detected" khi phát hiện khuôn mặt.
- Ghi log các lần phát hiện khuôn mặt vào log.txt.
- Lưu ảnh cuối cùng có khuôn mặt vào thư mục resuilt_haar_cascade_webcam/.
- Nhấn e hoặc Esc để thoát.

2. 🖼️ Nhận diện từ Ảnh
- Người dùng nhập đường dẫn đến ảnh đầu vào.
- Phát hiện khuôn mặt trong ảnh và vẽ khung.
- Hiển thị kết quả nhận diện.
- Lưu ảnh đã xử lý vào thư mục resuilt_haar_cascade_imgs/.


📂 Cấu trúc thư mục đầu ra
| Thư mục / Tệp                  | Mô tả                                                                          |
| ------------------------------ | ------------------------------------------------------------------------------ |
| `resuilt_haar_cascade_webcam/` | Lưu ảnh cuối cùng từ webcam có chứa khuôn mặt.                                 |
| `resuilt_haar_cascade_imgs/`   | Lưu ảnh đầu ra đã nhận diện từ ảnh người dùng cung cấp.                        |
| `log.txt`                      | Ghi log thời gian và số lượng khuôn mặt phát hiện trong mỗi khung hình webcam. |

▶️ Cách sử dụng
1. Cài đặt thư viện cần thiết
 """"pip install opencv-python""""
2. Chạy chương trình


✅ Ghi chú
- Sử dụng mô hình haarcascade_frontalface_default.xml có sẵn trong OpenCV để nhận diện khuôn mặt.
- Dừng quét webcam bằng phím e hoặc Esc.


👤 Nhận Diện Khuôn Mặt bằng DeepFace

🧠 Chức năng chính
Chương trình sử dụng thư viện DeepFace để nhận diện và phân tích các đặc điểm trên khuôn mặt như:
        - 👶 Tuổi (age)
        - 🚻 Giới tính (gender)
        - 😊 Cảm xúc (emotion)
Có thể thực hiện với ảnh tĩnh hoặc webcam theo thời gian thực, đồng thời lưu ảnh và thông tin phân tích vào thư mục kết quả.

🚀 Các chế độ hoạt động
1. 🖼️ Phân tích từ Ảnh
- Nhập đường dẫn ảnh từ người dùng.
- Phân tích khuôn mặt để xác định:
        - Tuổi (Age)
        - Giới tính (Gender)
        - Cảm xúc chủ đạo (Emotion)
- Vẽ khung và hiển thị thông tin trên khuôn mặt.
- Lưu ảnh và thông tin vào thư mục result_deepface/.

2. 🎥 Phân tích từ Webcam
- Mở webcam và quét các khung hình theo thời gian thực.
- Với mỗi khung hình:
        - Phát hiện khuôn mặt.
        - Phân tích tuổi, giới tính và cảm xúc.
        - Vẽ kết quả trực tiếp lên màn hình.
- Lưu ảnh cuối cùng và thông tin nhận diện vào thư mục result_deepface/.
- Nhấn e hoặc Esc để thoát.

📂 Cấu trúc thư mục đầu ra
| Đường dẫn          | Nội dung lưu trữ                                                         |
| ------------------ | ------------------------------------------------------------------------ |
| `result_deepface/` | Lưu ảnh đầu ra (`.jpg`) và thông tin nhận diện (`.txt`) từ ảnh & webcam. |


🧩 Ghi chú kỹ thuật
✅ Sử dụng enforce_detection=False để tránh lỗi nếu không phát hiện được khuôn mặt.
✅ Hàm is_gui_available() đảm bảo chương trình hoạt động ổn định trên Linux headless server (không có màn hình).
✅ DeepFace sử dụng backend 'retinaface' cho hiệu quả nhận diện cao.
✅ Ảnh có thể chứa nhiều khuôn mặt, kết quả được đánh số #1, #2, ... để dễ theo dõi.
✅ Kết quả được ghi ra cả ảnh có chú thích và file .txt chứa thông tin.

🧱 Yêu cầu cài đặt
pip install deepface opencv-python TensorFlow

📌 Ví dụ file đầu ra (.txt)
Thông tin nhận diện từ ảnh: /path/to/image.jpg
#1: Gender: Woman | Age: 25 | Emotion: happy
#2: Gender: Man | Age: 33 | Emotion: neutral

📷 Demo ảnh kết quả 
result_deepface/
├── deepface_input1.jpg
├── deepface_input1.txt
├── deepface_webcam_20250727_113201.jpg
└── deepface_webcam_20250727_113201.txt

🧩 Ghi chú kỹ thuật
- Hàm is_gui_available() giúp chương trình chạy được trên các môi trường không có giao diện hiển thị (Linux headless).
- DeepFace sử dụng enforce_detection=False để tránh lỗi nếu không phát hiện được khuôn mặt.