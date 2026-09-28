# Top 5000 YouTube Channels — Exploratory Data Analysis

An EDA project on the top 5,000 YouTube channels dataset using **Python**, **Pandas**, **Matplotlib**, and **Seaborn**, exploring channel grades, video uploads, subscribers, and views — including correlation analysis between these metrics.

## 📊 About the Dataset

File: `6-top-5000-youtube-channels.csv` — 5,000 rows × 6 columns (after cleaning).

| Column | Original Name | Description |
|---|---|---|
| Rank | Rank | Channel's rank (cleaned from text like "1st" to integer) |
| Grade | Grade | Channel grade (A++, A+, A, A-, B+) |
| channel_name | Channel name | Name of the YouTube channel |
| video_upload | Video Uploads | Number of videos uploaded |
| Subscribers | Subscribers | Number of subscribers |
| video_views | Video views | Total video views |

**Data cleaning performed:**
- Renamed `Video views` → `video_views`, `Video Uploads` → `video_upload`, `Channel name` → `channel_name`.
- Stripped commas and ordinal suffixes (e.g., "1st" → "1") from `Rank`, converted to integer.
- Replaced `--` placeholders in `Subscribers` and `video_upload` with `0`, removed stray whitespace, converted both to numeric/integer using `pd.to_numeric()` with `errors='coerce'`.
- Converted `video_views` to integer.

## 🎯 Purpose

To explore what separates top-performing YouTube channels — which channels lead in uploads and views, how channel grade relates to upload volume, and how strongly subscribers, uploads, and views correlate with each other.

## 🛠️ Approach

1. **Load and clean** the raw dataset — fix column names, strip text artifacts, convert types.
2. **Inspect structure** — `info()` to confirm clean numeric types across all 5,000 rows.
3. **Grade distribution** — count channels per `Grade` using `groupby()`.
4. **Top performers** — identify the channel with the most uploads and the most views; rank top 5 by uploads and top 3 by views.
5. **Grade-wise leaders** — find the top-uploading channel within each grade.
6. **Correlation analysis** — compute a correlation matrix and visualize it as a heatmap.
7. **Visualization** — bar plot (top 5 by uploads), line plot (top 3 by views), scatter plot (grade vs. top upload count).

## ❓ Questions Answered

- What does the raw dataset look like, and what cleaning does it need?
- How many channels fall into each grade (A++, A+, A, A-, B+)?
- Which channel has uploaded the most videos?
- Which 5 channels have the most video uploads?
- Which channel has the most total video views?
- Which 3 channels have the most video views?
- Within each grade, which channel uploaded the most videos?
- What is the correlation between Rank, video uploads, subscribers, and video views?
- What is the average number of video views across all 5,000 channels?

## 🗄️ Tech Stack

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**

## 📁 Repository Structure

```
├── top_5000_youtube_.ipynb   # Notebook with code, outputs, and visualizations
├── Project_Report.docx       # Full project report
└── README.md
```

## 🚀 How to Run

1. Install the requirements:
   ```
   pip install pandas numpy matplotlib seaborn jupyter
   ```
2. Place `6-top-5000-youtube-channels.csv` in the working directory (update the file path in the notebook if needed — the original path points to a Google Drive mount).
3. Open and run the notebook:
   ```
   jupyter notebook top_5000_youtube_.ipynb
   ```

## 📌 Key Findings

- The dataset has **5,000 channels** across grades **A++, A+, A, A-, and B+**; the vast majority (**2,956**) fall into grade **B+**.
- **AP Archive** has the most video uploads of any channel: **422,326** videos.
- **T-Series** has the most total video views: **~47.5 billion**, ahead of WWE (~26.3 billion) and Ryan ToysReview (~24.5 billion).
- Average video views across all 5,000 channels: **~1.07 billion**.
- **Subscribers and video views are strongly correlated (r ≈ 0.79)** — the strongest relationship in the dataset.
- **Rank correlates negatively** with both subscribers (r ≈ -0.36) and video views (r ≈ -0.39), confirming that a lower rank number means higher subscribers/views, as expected.
- **Video uploads show almost no correlation** with subscribers (r ≈ 0.02) or views (r ≈ 0.09) — uploading more videos does not reliably translate into more subscribers or views.

---
*An exploratory data analysis project on top YouTube channel performance metrics.*
