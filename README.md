# Twitter Sentiment Analysis
## Project Overview
This project involves building, training, and deploying an Artificial Intelligence (AI) model to predict the sentiment of thousands of tweets. The core objective is to understand public feeling towards a product or service by analyzing text data.

In the modern digital age, AI/ML-based sentiment analysis tools empower companies to automatically monitor customer feedback. This process eliminates the need for manual review of thousands of tweets, allowing businesses to gauge whether their customers are happy or not efficiently.

---

## Objectives
The primary goals of this project are:

- To perform Exploratory Data Analysis (EDA) and visualize text data.

- To clean text data by removing punctuation and stopwords.

- To perform Tokenization and Count Vectorization using Scikit-Learn.

- To understand and implement a **Naive Bayes Classifier**.

- To evaluate the model's performance using various Key Performance Indicators (KPIs) such as accuracy, precision, recall, and the confusion matrix.

---

## Tech Stack & Tools
The project is implemented using **Python** and the following libraries:

- **Pandas:** For data manipulation and analysis.

- **Numpy:** For numerical operations.

- **Seaborn & Matplotlib:** For data visualization (heatmaps, plots).

- **Scikit-Learn:** For machine learning models (Naive Bayes) and evaluation metrics.

- **WordCloud:** For visualizing common words in the dataset.

---

## Dataset
- **Input:** The dataset consists of Twitter tweets (text data).

- **Output:** A binary sentiment label:

  - **`0`:** Indicates positive or neutral sentiment (Normal tweets).

  - **`1`:** Indicates negative sentiment (Hate speech or unhappy tweets).

- **Size:** The dataset contains 31,962 entries.

---

## Project Pipeline
### 1. Data Import & Exploration

- Loaded the `twitter.csv` dataset using Pandas.

- Performed an initial inspection of the data (`info()`, `describe()`) to check for null values and understand the data types.

- Visualized missing data using a **Seaborn Heatmap** to ensure data integrity.

### 2. Exploratory Data Analysis (EDA)

- Analyzed the length of tweets to check the distribution of message sizes.

- Visualized the balance between the two sentiment classes (0 vs 1). Note: The classification report suggests an imbalanced dataset with significantly more Class 0 samples.

- Generated **Word Clouds** to visualize the most frequent words used in both positive and negative tweets.

### 3. Data Cleaning & Preprocessing

- **Punctuation Removal:** Stripped tweets of unnecessary punctuation marks.

- **Stopwords Removal:** Removed common words (e.g., "and", "the", "is") that do not contribute significant meaning to the sentiment.

- **Pipeline:** Created a cleaning pipeline to process the raw text into clean, analyzable tokens.

### 4. Feature Extraction (Tokenization)

- Used **CountVectorization** from Scikit-Learn to convert the cleaned text into numerical vectors. This transforms the text into a format that the machine learning model can understand (Bag of Words model).

### 5. Model Training

- Split the dataset into training and testing sets (standard train-test split).

- Implemented a **Naive Bayes Classifier** (`MultinomialNB`), a probabilistic algorithm well-suited for text classification tasks due to its efficiency with high-dimensional data.

### 6. Model Evaluation
The model was evaluated on the testing set using the following metrics:

- **Confusion Matrix:** To visualize true positives, true negatives, false positives, and false negatives.

- **Classification Report:**

  - **Accuracy:** Achieved an overall accuracy of **~95%**.

  - **Precision & Recall:**

    - Class 0 (Positive/Normal): High precision (0.97) and recall (0.97).

    - Class 1 (Negative): Precision of 0.61 and recall of 0.56.

  - **F1-Score:** The weighted average of precision and recall was 0.94 overall.

 ---

## Key Results

The Naive Bayes model demonstrated strong performance in identifying normal tweets (Class 0) but faced challenges with the minority class (Class 1), which is common in imbalanced datasets.

| Class / Metric | Precision | Recall | F1-Score | Support |
|--------------|-----------|--------|----------|---------|
| **`0` (Positive / Neutral Tweet)**| 0.97      | 0.97   | 0.97     | 5954    |
| **`1` (Negative Tweet)**| 0.61      | 0.56   | 0.59     | 439     |
| **Accuracy** |           |        | **0.95** | 6393    |
| **Macro Avg**| 0.79      | 0.77   | 0.78     | 6393    |
| **Weighted Avg**|0.94    | 0.95   | 0.94     | 6393    |

---
