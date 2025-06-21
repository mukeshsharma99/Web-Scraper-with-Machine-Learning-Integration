# 📚 Book Sentiment Analyzer with Web Scraping & Machine Learning

This project extracts book titles and star ratings from the public website [Books to Scrape](http://books.toscrape.com), performs sentiment classification using supervised machine learning models, and applies clustering to uncover patterns using unsupervised learning techniques.

---

## 🧠 Project Overview
    
### 🎯 Problem Statement
The project aims to build a web scraper to extract book titles and star ratings from 'Books to Scrape'. The scraped data is analyzed with:  
- **Supervised Learning** to classify reviews as positive or negative.
- **Unsupervised Learning** to group reviews into natural clusters. 

> ⭐ Positive: 4–5 stars  
> ⚠️ Negative: 1–3 stars

---
  
## 🕸️ Web Scraper Details

- **Tools Used**: `requests`, `BeautifulSoup`
- **Headers**: Custom `User-Agent` to mimic browser behavior.
- **Ethical Practice**: 1-second delay between requests to prevent server overload.
- **Data Extracted**:
  - `Title` of the book (used as proxy for review text)
  - `Star Rating` (converted to numerical 1–5) 

---

## 🧹 Preprocessing

- Removed special characters with `regex`
- Lowercased text
- Removed stopwords using `NLTK`
- Transformed text to numerical vectors using **TF-IDF**

---

## 🤖 Machine Learning Workflow

### 🔍 Supervised Learning (Classification)

| Model                | Purpose                                  |
|---------------------|------------------------------------------|
| Logistic Regression | Simple, interpretable baseline model     |
| Random Forest       | Robust to overfitting, handles feature interactions |
| XGBoost             | High performance on small datasets       |
| SVM                 | Works well with high-dimensional data    |

- **Target**: Sentiment Classification (Positive or Negative)
- **Evaluation**: Accuracy, Precision, Recall

### 🔗 Unsupervised Learning (Clustering)

- **Model**: `KMeans`
- **Use Case**: Discover hidden structure in reviews
- **Visualization**: TF-IDF → PCA (2D) → Cluster Plot

---

## 🧮 Mathematical Concepts

| Concept        | Application                                  |
|----------------|----------------------------------------------|
| Statistics     | Word frequency, TF-IDF                       |
| Linear Algebra | TF-IDF vectors, PCA dimensionality reduction |
| Probability    | Logistic Regression model                    |
| Optimization   | Gradient Descent (Logistic Regression, SVM)  |
| Distance       | Euclidean distance (KMeans clustering)       |

---

## 🌟 Word Cloud Visualizations

- Word clouds generated for both **Positive** and **Negative** reviews to highlight dominant terms in each sentiment group.

---

## 🔧 Key Challenges & Solutions

| Challenge                                | Solution                                                       |
|-----------------------------------------|----------------------------------------------------------------|
| Special characters & stopwords          | Regex cleaning + NLTK stopword removal                         |
| Risk of being blocked while scraping    | Used polite headers and time delays (1s between requests)      |
| Small dataset                           | TF-IDF + Regularization to prevent overfitting                 |
| High-dimensional vector visualization   | PCA used to reduce dimensions and visualize clusters in 2D     |

---

## ✅ Results

- Strong performance on sentiment classification tasks using limited data.
- Successful clustering revealed natural groupings in review text.

---

## 🔮 Future Work

- Expand dataset by scraping all available pages.
- Use `GridSearchCV` for hyperparameter optimization.
- Integrate deep learning (e.g., **BERT**) for more accurate sentiment detection.
- Develop a **web application** for real-time sentiment predictions.

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/book-sentiment-analyzer.git
   cd book-sentiment-analyzer
