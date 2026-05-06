# 🏊 Pozar Thermal Baths — TripAdvisor Sentiment & Topic Analysis

Analysis of **866 TripAdvisor reviews** for Pozar Thermal Baths (Λουτρά Πόζαρ, Greece) using Natural Language Processing (NLP) techniques.

---

## 📋 Project Overview

This project performs sentiment analysis and topic detection on Greek/multilingual TripAdvisor reviews to identify:
- Overall visitor satisfaction
- Most discussed topics (water, cleanliness, staff, etc.)
- Which aspects drive positive or negative experiences

---

## 📁 Repository Structure

```
pozar-sentiment-analysis/
│
├── Pozar_Sentiment_Analysis_EN.ipynb   # Main analysis notebook
├── Pozar_TripAdvisor_Reviews.xlsx      # Dataset (866 reviews)
└── README.md                           # This file
```

---

## 📊 Dataset

| Field | Description |
|-------|-------------|
| `title` | Review title |
| `rating` | Star rating (1–5) |
| `travelType` | Type of trip (Couples, Friends, Solo, etc.) |
| `text` | Full review text |

- **Source:** tripadvisor.com.gr
- **Collection method:** Web Scraper Chrome extension
- **Total reviews:** 866
- **Languages:** Greek, English

---

## 🤖 Methods

### Sentiment Analysis
- **Model:** [`nlptown/bert-base-multilingual-uncased-sentiment`](https://huggingface.co/nlptown/bert-base-multilingual-uncased-sentiment)
- **Architecture:** BERT (Bidirectional Encoder Representations from Transformers)
- **Languages supported:** Dutch, English, French, German, Italian, Spanish, Greek
- **Output mapping:**
  - ⭐⭐⭐⭐–⭐⭐⭐⭐⭐ → **Positive**
  - ⭐⭐⭐ → **Neutral**
  - ⭐–⭐⭐ → **Negative**

### Topic Analysis
- **Method:** Keyword-based topic detection
- **Topics identified:**

| Topic | Example Keywords |
|-------|-----------------|
| Water / Pools | νερό, πισίνα, καταρράκτης |
| Cleanliness | καθαριότητα, βρώμικο, υγιεινή |
| Staff | προσωπικό, εξυπηρέτηση, αγένεια |
| Facilities | αποδυτήρια, εγκαταστάσεις, δωμάτιο |
| Prices | τιμή, ακριβό, εισιτήριο |
| Nature / Scenery | φύση, τοπίο, καστανιές |
| Food / Café | φαγητό, καφέ, εστιατόριο |
| Crowds / Waiting | κόσμος, αναμονή, ουρά |

---

## 📈 Visualizations

The notebook produces the following charts:

1. **EDA Overview** — Rating distribution, travel type breakdown, avg rating per travel type
2. **Rating Split** — Review length by rating, positive/neutral/negative pie chart
3. **Sentiment Analysis** — Sentiment distribution, rating vs sentiment heatmap, sentiment by travel type
4. **Topic Analysis** — Topic frequency, average rating per topic
5. **Word Clouds** — Most frequent words in positive vs negative reviews
6. **Sentiment per Topic** — Stacked bar showing sentiment breakdown per topic

---

## 🚀 How to Run

### Option A: Google Colab (recommended)
1. Open [Google Colab](https://colab.research.google.com)
2. Upload `Pozar_Sentiment_Analysis_EN.ipynb`
3. Run all cells (Runtime → Run all)
4. Upload `Pozar_TripAdvisor_Reviews.xlsx` when prompted

> 💡 **Tip:** For faster execution, switch to GPU: Runtime → Change runtime type → T4 GPU

### Option B: Local (Jupyter)
```bash
pip install transformers torch wordcloud pandas matplotlib seaborn openpyxl
jupyter notebook Pozar_Sentiment_Analysis_EN.ipynb
```

---

## 🛠️ Libraries Used

| Library | Version | Purpose |
|---------|---------|---------|
| `transformers` | 4.x | BERT sentiment model |
| `torch` | 2.x | Model inference |
| `pandas` | 2.x | Data manipulation |
| `matplotlib` | 3.x | Visualization |
| `seaborn` | 0.x | Statistical charts |
| `wordcloud` | 1.x | Word cloud generation |

---

## 📄 License

This project is for academic purposes only. Review data belongs to TripAdvisor and respective authors.
