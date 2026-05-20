#  Popularity Prediction for Spotify Tracks using Machine Learning

This project uses Python to analyze Spotify song data in order to explore the factors influencing song popularity and build Machine Learning models to predict popularity based on audio features.
Through analyzing Spotify user listening behavior, the project aims to provide practical applications in the music production and entertainment event industry.

## Project Objectives

The project focuses on analyzing the relationship between Spotify audio features and song popularity to better understand consumer listening behavior.

Based on popularity analysis results, the project aims to support practical applications such as:

- Assisting music producers in identifying song characteristics that better match listener preferences.
- Supporting event organizers in selecting songs with suitable characteristics to improve audience engagement.


## Team Members & Task Distribution
This project was developed by **[GROUP 6]**, with each member contributing to specific parts of the workflow as follows:

| Full Name | Role | Contribution Details |
| :--- | :--- | :--- |
| **Vũ Hoàng Thục Quyên** | Team Leader / Data Engineer | Proposed project ideas and developed `02_LamSachDuLieu.ipynb`, including missing value handling, duplicate row removal, `track_id` deduplication workflow construction, outlier handling using the IQR method, and data standardization for Machine Learning model training. Participated in developing `03_HuanLuyenModel.ipynb`. |
| **Nguyễn Thị Thanh Thuý** | Data Quality Analyst | Contributed project ideas and developed `02_LamSachDuLieu.ipynb`, including post-cleaning data quality checking, audio feature consistency validation, duplicate data processing support, preprocessing validation before model training, and exporting the cleaned dataset. Participated in developing `03_HuanLuyenModel.ipynb`. |
| **Dương Minh Ánh** | EDA Analyst | Developed `01_KhamPhaDuLieu.ipynb`, explored dataset structure, checked missing values and duplicate values, performed data visualization, and analyzed relationships between Spotify audio features and song popularity. Participated in developing `03_HuanLuyenModel.ipynb`. |
| **Nguyễn Hải Yến** | Visualization Analyst | Collected dataset resources and contributed to `01_KhamPhaDuLieu.ipynb`, supported EDA analysis, created visualization charts such as `Genre Popularity`, `Artist Popularity`, and `Correlation Matrix`, and summarized insights regarding Spotify user listening behavior. Participated in developing `03_HuanLuyenModel.ipynb`. |

**During the Machine Learning modeling phase, all team members collaboratively contributed to developing and improving `03_HuanLuyenModel.ipynb`.**

- Each member experimented with different Machine Learning algorithms, preprocessing techniques, model evaluation approaches, and hyperparameter tuning strategies to identify the most suitable solution for the popularity prediction problem.
- After comparing experimental results, the team leader was responsible for consolidating, selecting, and optimizing the best-performing implementations to create the final version of the project model.


**Trong giai đoạn xây dựng mô hình Machine Learning, tất cả thành viên trong nhóm đều tham gia phát triển và hoàn thiện file `03_HuanLuyenModel.ipynb`.**
- Mỗi thành viên thực hiện thử nghiệm các thuật toán, phương pháp tiền xử lý dữ liệu, kỹ thuật đánh giá mô hình và tối ưu tham số khác nhau nhằm tìm ra hướng tiếp cận phù hợp nhất cho bài toán dự đoán popularity.
- Sau quá trình thử nghiệm và so sánh kết quả, trưởng nhóm chịu trách nhiệm tổng hợp, lựa chọn và tối ưu các phần triển khai hiệu quả nhất để xây dựng phiên bản mô hình cuối cùng của dự án.
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
└── Requirements.txt                <- Danh sách các thư viện cần cài đặt
```

## Nguồn dữ liệu (Data Source)
* Dữ liệu được thu thập từ:
  - **Dataset**: Spotify Tracks Dataset
  - **Source**: Kaggle
  - **Link**:  https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset
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

**Ngoài việc đánh giá hiệu suất dự đoán, dự án còn thực hiện phân tích residual distribution, actual vs predicted scatter plot và permutation importance nhằm giải thích khả năng dự đoán của mô hình và xác định các audio features ảnh hưởng mạnh nhất đến popularity.**
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

1. Clone repository về máy:

```bash
https://github.com/thuysforwork-cloud/popularity-prediction-ml.git
```

2. Cài đặt các thư viện cần thiết:

```bash
pip install -r Requirements.txt
```

3. Mở project bằng VSCode hoặc Jupyter Notebook.

4. Đảm bảo cấu trúc thư mục giữ nguyên như repository gốc:

```bash
popularity-prediction-ml/
│
├── data/
│   ├── raw_data.csv
│   └── cleaned_data.csv
│
├── notebooks/
│   ├── 01_KhamPhaDuLieu.ipynb
│   ├── 02_LamSachDuLieu.ipynb
│   └── 03_HuanLuyenModel.ipynb
│
├── README.md
└── Requirements.txt
```

5. Chạy lần lượt các notebook trong thư mục `notebooks/` theo thứ tự:

- `01_KhamPhaDuLieu.ipynb`
- `02_LamSachDuLieu.ipynb`
- `03_HuanLuyenModel.ipynb`

6. Các notebook đã được cấu hình tự động nhận diện đường dẫn dữ liệu thông qua `Path.cwd()`, vì vậy người dùng chỉ cần mở project đúng cấu trúc thư mục ban đầu.
