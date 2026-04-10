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
