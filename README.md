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

## Repository Structure
```bash
popularity-prediction-ml/
│
├── data/                           <- Dataset directory
│   ├── raw_data.csv                <- Original raw dataset
│   └── cleaned_data.csv            <- Cleaned dataset used for modeling
│
├── notebooks/                      <- Jupyter Notebook directory
│   ├── 01_KhamPhaDuLieu.ipynb      <- Step 1: Exploratory Data Analysis
│   ├── 02_LamSachDuLieu.ipynb      <- Step 2: Data Cleaning & Preprocessing
│   └── 03_HuanLuyenModel.ipynb     <- Step 3: Machine Learning Modeling
│
└── README.md                       <- Project documentation
└── Requirements.txt                <- Required Python libraries
```

## Data Source
Data was collected from:
  - **Dataset**: Spotify Tracks Dataset
  - **Source**: Kaggle
  - **Link**:  https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset
    
**Short Description**: The dataset contains approximately **114,000 rows** and **20 columns**, including Spotify song information such as:
- popularity
- danceability
- energy
- loudness
- valence
- acousticness
- tempo
- instrumentalness
- artist information
- music genre
- duration
- explicit content

## Project Workflow
### Exploratory Data Analysis (EDA)

The EDA process focuses on:

- Exploring dataset structure
- Detecting missing values and duplicate values
- Analyzing data distributions
- Visualizing relationships between audio features and popularity
- Analyzing popularity across genres and artists
- Exploring Spotify user listening behavior trends

Key analyses include:

- Loudness vs Popularity
- Explicit Content vs Popularity
- Genre Popularity Analysis
- Artist Popularity Analysis
- Correlation Matrix Analysis

---

### Data Cleaning

Data preprocessing includes:

- Removing unnecessary columns
- Handling missing values
- Removing duplicate values
- Deduplicating repeated `track_id` entries
- Handling outliers using the IQR method
- Standardizing features before model training

After preprocessing, the cleaned dataset is stored as:

```bash
cleaned_data.csv
```

---

### Machine Learning Model

The project builds Machine Learning models to predict Spotify song popularity based on audio features.

The workflow includes:

- Train-test splitting
- Feature preprocessing
- Model training
- Hyperparameter tuning
- Model comparison
- Prediction performance evaluation
- Permutation importance analysis

The following Machine Learning algorithms were implemented and compared:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor

Among all tested models, the **Random Forest Regressor** achieved the best predictive performance.

---

### Model Evaluation Metrics

Models were evaluated using:

- MAE (Mean Absolute Error)
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)
- R² Score

Results indicate that the Random Forest model captures non-linear relationships between audio features and popularity more effectively than the other models.

In addition to prediction evaluation, the project also conducted:

- **Residual distribution analysis**
- **Actual vs Predicted scatter plot analysis**
- **Permutation importance analysis**

to better explain model behavior and identify the most influential audio features affecting popularity.

## Key Findings

### Data Insights

- Songs with higher energy and loudness tend to achieve higher popularity.
- Genres such as pop-film, k-pop, and chill show relatively high average popularity within the dataset.
- Explicit tracks tend to have slightly higher average popularity compared to non-explicit tracks.
- Popularity is influenced by combinations of musical characteristics rather than a single feature.
- Certain artists and artist collaborations demonstrate significantly higher average popularity.

Spotify songs with high popularity commonly exhibit:

- higher energy,
- louder sound levels,
- stronger rhythmic characteristics,
- and frequently belong to genres such as pop, k-pop, or dance-pop.

### Practical Applications

Based on the findings:

- Music producers may use these insights to better align music production styles with audience preferences.
- Entertainment event organizers may prioritize energetic and high-engagement songs to improve audience excitement and event atmosphere.

### Model Findings

- The Random Forest Regressor achieved the best overall predictive performance.
- Random Forest demonstrated superior capability in capturing non-linear relationships between audio features and popularity.
- Song popularity can be reasonably predicted using Spotify audio features.
- Permutation importance analysis revealed that features such as energy, loudness, danceability, and valence play important roles in popularity prediction.
---

## Hướng dẫn chạy code (How to run)

To reproduce the project results, follow these steps:

1. Clone the repository:

```bash
https://github.com/thuysforwork-cloud/popularity-prediction-ml.git
```

2. Install required libraries:

```bash
pip install -r requirements.txt
```

3. Open the project using VSCode or Jupyter Notebook.

4. Keep the repository structure unchanged:

```bash
popularity-prediction-ml/
│
├── data/
│ ├── raw_data.csv
│ └── cleaned_data.csv
│
├── notebooks/
│ ├── 01_KhamPhaDuLieu.ipynb
│ ├── 02_LamSachDuLieu.ipynb
│ └── 03_HuanLuyenModel.ipynb
│
├── README.md
└── requirements.txt
```

5. Run notebooks sequentially in the following order:

- `01_KhamPhaDuLieu.ipynb`
- `02_LamSachDuLieu.ipynb`
- `03_HuanLuyenModel.ipynb`

6. The notebooks are configured to automatically detect dataset paths using `Path.cwd()`, so users only need to maintain the original repository structure. 
