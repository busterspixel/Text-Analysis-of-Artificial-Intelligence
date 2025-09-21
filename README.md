# AI in the News: A Sentiment and Topic Analysis Project

This project conducts a detailed analysis of news headlines related to **Artificial Intelligence**. It leverages Natural Language Processing (NLP) techniques to process raw news titles, uncover public sentiment, identify key discussion topics, and discover common word patterns.



## 📜 Project Overview

The goal of this project is to gain data-driven insights from the media's portrayal of AI. By analyzing a large dataset of news headlines, we can answer questions like:
* **Media Sentiment:** Is the news coverage of AI predominantly positive, negative, or neutral?
* **Key Topics:** What are the most significant themes and talking points in the AI news cycle? (e.g., AI ethics, new models, industry applications).
* **Common Phrases:** What are the most frequent word pairs (bigrams) and triplets (trigrams) used when discussing AI?

The analysis pipeline is built with Python and utilizes a suite of powerful data science libraries, including Pandas, NLTK, TextBlob, Scikit-learn, and Matplotlib.

## ✨ Features

* **Text Preprocessing**: A robust pipeline to clean and prepare raw news headlines for analysis.
* **Sentiment Analysis**: Uses `TextBlob` to assign a sentiment score to each headline, classifying it as **Positive**, **Negative**, or **Neutral**.
* **Topic Modeling**: Implements **TF-IDF** and **NMF** (Non-negative Matrix Factorization) to automatically extract 5 key topics from the headlines.
* **N-gram Analysis**: Identifies and ranks the most common **bigrams** (two-word phrases) and **trigrams** (three-word phrases) to understand common terminology and collocations.
* **Data Visualization**: Creates a variety of plots for easy interpretation of the results:
    * **Pie Chart** for sentiment distribution.
    * **Bar Charts** for the top words in each topic.
    * **Word Clouds** for a high-impact visual representation of topic keywords.

## 📦 Requirements

To run this project, you'll need Python 3 and the following libraries. You can easily install them using pip:

```bash
pip install pandas openpyxl nltk textblob scikit-learn matplotlib wordcloud
```

Additionally, the script requires NLTK data for tokenization and stopword removal. These will be downloaded automatically the first time you run the script. You can also download them manually in a Python environment:

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```

## 📊 Workflow & Usage

The project is structured as a sequential script. Follow these steps to run the analysis on your own data.

### 1. Data Input

Start with an Excel file (`.xlsx`) containing news headlines. The script expects the headlines to be in a column named **`title`**. Place this file in your project directory and update the `file_path` variable in the script:

```python
# Update with the path to your Excel file
file_path = r"C:\Users\ASUS\OneDrive\Desktop\dataset_google-news-scraper_AI2025-09-21_12-06-08-037.xlsx"
df = pd.read_excel(file_path)
```

### 2. Text Preprocessing & Sentiment Analysis

The script first cleans the `title` column and then performs sentiment analysis.
1.  **Preprocessing**: Text is tokenized, converted to lowercase, and stripped of special characters and stopwords. The processed data is saved to `AI1.xlsx`.
2.  **Sentiment Analysis**: A sentiment score and category are calculated for each headline. The final, enriched DataFrame is saved to `sentiment_analysis_resultsAI1.xlsx`.

### 3. Topic Modeling

Using the cleaned text from the results file, the script identifies 5 latent topics in the news headlines.
1.  Headlines are converted into a numerical TF-IDF matrix.
2.  An NMF model is trained to discover the topics.
3.  The top 10 words for each topic are printed to the console.

### 4. N-gram Analysis

This step analyzes word co-occurrence to find common phrases.
1.  All cleaned words from all headlines are gathered into a single list.
2.  The script identifies the most frequent two-word (bigram) and three-word (trigram) phrases.
3.  The top 20 most common bigrams and trigrams are printed to the console.

### 5. Visualization

Finally, the script generates several visualizations to summarize the findings, which will be displayed on your screen as the script runs.

## 📁 File Structure

```
.
├── your_ai_news_dataset.xlsx        # Your initial input data file
├── AI1.xlsx                         # Intermediate file with preprocessed text
├── sentiment_analysis_resultsAI1.xlsx # Final output file with sentiment and topics
└── ai_news_analysis.py              # Your main Python script
```

## ⚖️ License

This project is licensed under the MIT License.
