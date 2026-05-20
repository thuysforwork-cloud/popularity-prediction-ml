#  Popularity Prediction for Spotify Tracks using Machine Learning
Dự án sử dụng Python để phân tích dữ liệu bài hát trên Spotify nhằm khám phá các yếu tố ảnh hưởng đến độ phổ biến (popularity) của bài hát và xây dựng mô hình Machine Learning dự đoán popularity dựa trên các đặc trưng âm nhạc.
Thông qua việc phân tích hành vi nghe nhạc của người dùng Spotify, dự án hướng tới ứng dụng thực tiễn trong lĩnh vực sản xuất âm nhạc và tổ chức sự kiện giải trí.
## Mục tiêu dự án
Dự án tập trung phân tích mối quan hệ giữa các đặc trưng âm nhạc và độ phổ biến của bài hát trên Spotify nhằm hiểu rõ hơn về hành vi nghe nhạc của người dùng.
Từ kết quả phân tích popularity, dự án hướng tới các ứng dụng thực tiễn như:
Hỗ trợ nhà sản xuất âm nhạc định hướng phong cách và đặc điểm bài hát phù hợp với thị hiếu người nghe.
Hỗ trợ người tổ chức sự kiện lựa chọn các bài hát có đặc điểm phù hợp nhằm tăng mức độ thu hút khán giả.

## Thành viên nhóm & Phân công công việc
Dự án được thực hiện bởi nhóm **[NHÓM 6]**, với sự đóng góp cụ thể của từng thành viên như sau:
| Họ và Tên | Vai trò | Chi tiết công việc thực hiện |
| :--- | :--- | :--- |
| **Vũ Hoàng Thục Quyên** | Trưởng nhóm / Data Engineer | Lên ý tưởng, và viết file `02_LamSachDuLieu.ipynb`, xử lý missing values, loại bỏ duplicate rows, xây dựng quy trình deduplicate theo `track_id`, xử lý outliers bằng phương pháp IQR và chuẩn hóa dữ liệu phục vụ huấn luyện mô hình Machine Learning. Tham gia viết file `03_HuanLuyenModel.ipynb` |
| **Nguyễn Thị Thanh Thuý** | Data Quality Analyst | Lên ý tưởng, viết file `02_LamSachDuLieu.ipynb`, kiểm tra chất lượng dữ liệu sau làm sạch, rà soát tính nhất quán của các audio features, hỗ trợ xử lý dữ liệu trùng lặp và kiểm tra kết quả preprocessing trước khi đưa vào giai đoạn huấn luyện mô hình và xuất ra file data chuẩn. Tham gia viết file `03_HuanLuyenModel.ipynb` |
| **Dương Minh Ánh** | EDA Analyst | Viết file `01_KhamPhaDuLieu.ipynb`, khám phá cấu trúc dữ liệu, kiểm tra missing values và duplicate values, thực hiện trực quan hóa dữ liệu và phân tích mối quan hệ giữa các audio features với popularity của bài hát trên Spotify. Tham gia viết file  `03_HuanLuyenModel.ipynb` |
| **Nguyễn Hải Yến** | Visualization Analyst | Tìm kiếm dữ liệu, Tham gia Viết file `01_KhamPhaDuLieu.ipynb` hỗ trợ phân tích EDA, xây dựng các biểu đồ trực quan hóa như `Genre Popularity`, `Artist Popularity` và `Correlation Matrix`, đồng thời tổng hợp insight và phân tích xu hướng nghe nhạc của người dùng Spotify từ dataset. Tham gia viết file  `03_HuanLuyenModel.ipynb` |

## Cấu trúc Repository 
```bash
popularity-prediction-ml/
│
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
```

## Nguồn dữ liệu (Data Source)
* Dữ liệu được thu thập từ:
  - [Dataset: Spotify Tracks Dataset]
  - [Source:Kaggle]
  - Link: [https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset?fbclid=IwY2xjawR6Z5VleHRuA2FlbQIxMABicmlkETEwUXlPTXZEeHZHSk9CTGUzc3J0YwZhcHBfaWQQMjIyMDM5MTc4ODIwMDg5MgABHvccSChIKJnZsfyoaTQl4-2bZFdDJAIn4mDYwrldRkAPHQoa1SOU6_YNUOJ5_aem_3URjtBLYBrmHS0cgnzX6cQ)]
* Mô tả ngắn: Tập dữ liệu gồm khoảng 114,000 dòng và 20 cột, chứa các thông tin liên quan đến bài hát trên Spotify như
  - độ phổ biến (popularity),
  - đặc trưng âm thanh (danceability, energy, loudness, valence, tempo, acousticness, instrumentalness),
  - thông tin nghệ sĩ,
  - thể loại nhạc (genre),
  - duration 
  - explicit content.

## Quy trình thực hiện
### Exploratory Data Analysis (EDA)

Quá trình EDA tập trung vào:

- Khám phá cấu trúc dữ liệu
- Kiểm tra missing values và duplicate values
- Phân tích phân phối dữ liệu
- Trực quan hóa mối quan hệ giữa các audio features và popularity
- Phân tích popularity giữa các genre và nghệ sĩ
- Khám phá xu hướng nghe nhạc của người dùng Spotify

Các phân tích nổi bật gồm:

- Energy vs Popularity
- Loudness vs Popularity
- Explicit Content vs Popularity
- Genre Popularity Analysis
- Artist Popularity Analysis
- Correlation Matrix Analysis

---

### Data Cleaning

Dữ liệu được làm sạch thông qua các bước:

- Xóa cột không cần thiết
- Xử lý missing values
- Loại bỏ duplicate values
- Deduplicate theo `track_id`
- Xử lý outliers bằng phương pháp IQR
- Chuẩn hóa dữ liệu trước khi huấn luyện mô hình

Sau khi xử lý, dữ liệu sạch được lưu dưới dạng:

```bash
cleaned_data.csv
```

---

### Machine Learning Model

Dự án xây dựng mô hình Machine Learning nhằm dự đoán độ phổ biến của bài hát dựa trên các đặc trưng âm nhạc.

Quy trình gồm:

- Chia train/test set
- Feature preprocessing
- Huấn luyện mô hình
- Hyperparameter tuning
- Model comparison
- Đánh giá hiệu suất dự đoán
- Permutation importance analysis

Các thuật toán Machine Learning được sử dụng để so sánh và đánh giá khả năng dự đoán popularity gồm:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor

Trong các mô hình đã thử nghiệm, Random Forest Regressor đạt hiệu suất dự đoán tốt nhất.

---

### Model Evaluation Metrics

Các mô hình được đánh giá bằng:

- MAE (Mean Absolute Error)
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)
- R² Score

Kết quả cho thấy Random Forest có khả năng nắm bắt mối quan hệ phi tuyến giữa các audio features và popularity hiệu quả hơn các mô hình còn lại.

  Các đặc trưng này được sử dụng để phân tích hành vi nghe nhạc và xây dựng mô hình dự đoán popularity của bài hát.
## Kết quả nổi bật (Key Findings)
**Về dữ liệu:** 

* Các bài hát có mức energy và loudness cao thường xuất hiện nhiều hơn trong nhóm bài hát có popularity cao.
* Một số genre như pop-film, k-pop và chill có popularity trung bình nổi bật trong dataset.
* Explicit tracks có popularity trung bình nhỉnh hơn so với non-explicit tracks.
* Popularity không phụ thuộc hoàn toàn vào một đặc trưng đơn lẻ mà chịu ảnh hưởng từ nhiều yếu tố âm nhạc kết hợp.
* Một số nghệ sĩ và nghệ sĩ hợp tác có mức popularity trung bình cao hơn đáng kể trong dataset.

Từ kết quả phân tích dữ liệu Spotify, nhóm nhận thấy các bài hát có popularity cao thường mang một số đặc điểm chung như:

- mức energy cao hơn,
- âm lượng (loudness) lớn hơn,
- nhịp điệu sôi động,
- và xuất hiện nhiều ở các thể loại như pop, k-pop hoặc dance-pop.

Ngoài ra, các bài hát explicit cũng có xu hướng đạt popularity trung bình cao hơn trong dataset.

Từ những kết quả đó, dự án có thể được ứng dụng trong thực tế như:

- Nhà sản xuất âm nhạc có thể tham khảo các đặc điểm âm thanh phổ biến ở những bài hát được yêu thích để định hướng phong cách sản xuất phù hợp hơn với thị hiếu người nghe hiện nay.
- Người tổ chức sự kiện âm nhạc có thể ưu tiên lựa chọn các bài hát có đặc trưng sôi động, năng lượng cao hoặc thuộc các thể loại được nghe nhiều nhằm tăng khả năng khuấy động không khí và thu hút khán giả.

**Về mô hình:**
  - Random Forest Regressor đạt hiệu suất dự đoán tốt nhất trong các mô hình được thử nghiệm.
  - Mô hình Random Forest cho khả năng nắm bắt mối quan hệ phi tuyến giữa các audio features và popularity hiệu quả hơn các mô hình còn lại.
  - Kết quả dự đoán cho thấy popularity có thể được dự đoán tương đối tốt thông qua các đặc trưng âm nhạc trên Spotify.
  - Permutation importance analysis cho thấy các đặc trưng như energy, loudness, danceability và valence đóng vai trò quan trọng trong quá trình dự đoán popularity.

## Hướng dẫn chạy code (How to run)
Để tái tạo lại kết quả của nhóm, vui lòng thực hiện theo các bước sau:
1. Cài đặt các thư viện cần thiết: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.
2. Mở Jupyter Notebook và chạy lần lượt các file trong thư mục `notebooks/` theo thứ tự từ `01` đến `03`.
