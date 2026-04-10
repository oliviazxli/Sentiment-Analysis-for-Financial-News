# Sentiment Analysis for Financial News

**CDS525 Group Project | Group: AlgoRhythm**

## Project Overview
This project implements a financial news sentiment classification system based on a **FinBERT-BiLSTM-Attention** architecture. The model classifies financial news headlines into three sentiment categories: **positive**, **neutral**, and **negative**.

The system also includes a real-time REST API built with FastAPI and ngrok, enabling live sentiment prediction on financial news fetched from Google News RSS feed.

---

## Dataset
- **Source**: [Sentiment Analysis for Financial News](https://www.kaggle.com/datasets/ankurzing/sentiment-analysis-for-financial-news) (Kaggle)
- **Size**: ~4,700 samples
- **Labels**: positive, neutral, negative
- **Split**: Train 70% / Validation 20% / Test 10%

---

## Model Architecture
- **FinBERT** (ProsusAI/finbert): Domain-specific pre-trained language model
- **BiLSTM**: Captures sequential and contextual relationships
- **Self-Attention**: Focuses on sentiment-critical keywords
- **Loss Function**: Focal Loss (primary) vs CrossEntropy Loss (baseline)

---

## Experiments
| Experiment | Settings |
|---|---|
| Loss Function | Focal Loss vs CrossEntropy Loss |
| Learning Rate | 0.1, 0.01, 0.001, 0.0001 |
| Batch Size | 8, 16, 32, 64 |
| Epochs | 3 |

**Best Results**: Focal Loss + LR=2e-5 + BS=32 → Test Accuracy ~**83%**

---

## Project Structure
```
Sentiment-Analysis-for-Financial-News.ipynb        # Main Colab notebook (all code)
README.md             # Project documentation
```

---

## How to Run
1. Open `Sentiment-Analysis-for-Financial-News.ipynb` in Google Colab
2. Upload `all-data.csv` to Colab runtime
3. Run all cells in order
4. API will be accessible via ngrok public URL

---

## API Endpoints
| Endpoint | Description |
|---|---|
| `GET /predict?text=...` | Predict sentiment of a single text |
| `GET /latest_news_sentiment` | Fetch and predict latest 5 financial news |

---

## Results Summary
| Model | Test Accuracy |
|---|---|
| FinBERT-BiLSTM-Attention (Focal Loss) | ~83% |
| FinBERT-BiLSTM-Attention (CE Loss) | ~86% |

---

## Group Members
| Name | Student ID | Contribution |
|---|---|---|
| LI Zixin | 5599367 | Model Design and Training, Report, PPT |
| GE Chang | 5565990 | Visualization, PPT |
| LU Jiayun | 5513557 | Data Preprocessing, Report,PPT |
| MO Yiwen | 5571418 | API, Report，PPT |

---

## References
1. Devlin et al. (2019). BERT: Pre-training of Deep Bidirectional Transformers
2. Araci (2019). FinBERT: Financial Sentiment Analysis with Pre-trained Language Models
3. Yang et al. (2020). FinBERT: A Pre-trained Strategy for Financial NLP
