#  Popularity Prediction for Spotify Tracks using Machine Learning
Dự án sử dụng Python để phân tích dữ liệu bài hát trên Spotify nhằm khám phá các yếu tố ảnh hưởng đến độ phổ biến (popularity) của bài hát và xây dựng mô hình Machine Learning dự đoán popularity dựa trên các đặc trưng âm nhạc.
Thông qua việc phân tích hành vi nghe nhạc của người dùng Spotify, dự án hướng tới ứng dụng thực tiễn trong lĩnh vực sản xuất âm nhạc và tổ chức sự kiện giải trí.
# Mục tiêu dự án
Dự án tập trung phân tích mối quan hệ giữa các đặc trưng âm nhạc và độ phổ biến của bài hát trên Spotify nhằm hiểu rõ hơn về hành vi nghe nhạc của người dùng.
Từ kết quả phân tích popularity, dự án hướng tới các ứng dụng thực tiễn như:
Hỗ trợ nhà sản xuất âm nhạc định hướng phong cách và đặc điểm bài hát phù hợp với thị hiếu người nghe.
Hỗ trợ người tổ chức sự kiện lựa chọn các bài hát có đặc điểm phù hợp nhằm tăng mức độ thu hút khán giả.

## Thành viên nhóm & Phân công công việc
Dự án được thực hiện bởi nhóm [NHÓM 6], với sự đóng góp cụ thể của từng thành viên như sau:
| Họ và Tên | Vai trò | Chi tiết công việc thực hiện |
| :--- | :--- | :--- |
| **Vũ Hoàng Thục Quyên]** | Trưởng nhóm / | Lên ý tưởng, và viết file `02_LamSachDuLieu.ipynb`, xử lý missing values, loại bỏ duplicate rows, xây dựng quy trình deduplicate theo `track_id`, xử lý outliers bằng phương pháp IQR và chuẩn hóa dữ liệu phục vụ huấn luyện mô hình Machine Learning. Tham gia viết file `03_HuanLuyenModel.ipynb` |
| **[Nguyễn Thị Thanh Thuý]** | Lên ý tưởng, viết file `02_LamSachDuLieu.ipynb`, kiểm tra chất lượng dữ liệu sau làm sạch, rà soát tính nhất quán của các audio features, hỗ trợ xử lý dữ liệu trùng lặp và kiểm tra kết quả preprocessing trước khi đưa vào giai đoạn huấn luyện mô hình và xuất ra file data chuẩn. Tham gia viết file `03_HuanLuyenModel.ipynb` |
| **[Dương Minh Ánh]** | Viết file `01_KhamPhaDuLieu.ipynb`, khám phá cấu trúc dữ liệu, kiểm tra missing values và duplicate values, thực hiện trực quan hóa dữ liệu và phân tích mối quan hệ giữa các audio features với popularity của bài hát trên Spotify. Tham gia viết file  `03_HuanLuyenModel.ipynb` |
| **[Nguyễn Hải Yến]** | Tìm kiếm dữ liệu, Tham gia Viết file `01_KhamPhaDuLieu.ipynb` hỗ trợ phân tích EDA, xây dựng các biểu đồ trực quan hóa như `Genre Popularity`, `Artist Popularity` và `Correlation Matrix`, đồng thời tổng hợp insight và phân tích xu hướng nghe nhạc của người dùng Spotify từ dataset. Tham gia viết file  `03_HuanLuyenModel.ipynb` |

## Cấu trúc Repository 

├── data/                           <- Thư mục chứa dữ liệu
│   ├── raw_data.csv                <- Dữ liệu gốc tải về (Không chỉnh sửa)
│   └── cleaned_data.csv            <- Dữ liệu đã làm sạch (Dùng để chạy model)
│
├── notebooks/                      <- Thư mục chứa code Jupyter Notebook
│   ├── 01_KhamPhaDuLieu.ipynb      <- Bước 1: Khám phá và vẽ biểu đồ
│   ├── 02_LamSachDuLieu.ipynb      <- Bước 2: Xử lý dữ liệu lỗi
│   └── 03_HuanLuyenModel.ipynb     <- Bước 3: Chạy mô hình dự đoán
│
└── README.md                       <- Tài liệu hướng dẫn chung của dự án
└── requirements.txt                       <- Danh sách các thư viện cần cài đặt

## Nguồn dữ liệu (Data Source)
* Dữ liệu được thu thập từ:[Dataset: Spotify Tracks Dataset] [Source:Kaggle] [https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset?fbclid=IwY2xjawR6Z5VleHRuA2FlbQIxMABicmlkETEwUXlPTXZEeHZHSk9CTGUzc3J0YwZhcHBfaWQQMjIyMDM5MTc4ODIwMDg5MgABHvccSChIKJnZsfyoaTQl4-2bZFdDJAIn4mDYwrldRkAPHQoa1SOU6_YNUOJ5_aem_3URjtBLYBrmHS0cgnzX6cQ)]
* Mô tả ngắn: Tập dữ liệu gồm khoảng 114,000 dòng và 20 cột, chứa các thông tin liên quan đến bài hát trên Spotify như độ phổ biến (popularity), đặc trưng âm thanh (danceability, energy, loudness, valence, tempo, acousticness, instrumentalness), thông tin nghệ sĩ, thể loại nhạc (genre), duration và explicit content. Các đặc trưng này được sử dụng để phân tích hành vi nghe nhạc và xây dựng mô hình dự đoán popularity của bài hát.
* 
