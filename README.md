# Spam & Phishing Email Detection using NLP

A machine learning system that automatically classifies emails and SMS messages as **Safe (Ham)** or **Suspicious (Spam/Phishing)**. The model is trained on over 41,000 messages from three different datasets and achieves 96% F1 score using Logistic Regression.

## Problem Statement

Millions of people receive spam and phishing messages every day. While spam is just annoying, **phishing** is dangerous – it tricks users into revealing passwords, bank accounts, or personal information. This project builds an automatic detector that can identify both spam and phishing attempts, including social engineering tricks like "Hey, I lost my phone, send me your bank info."

## Datasets Used

| Dataset | Source | Size | Description |
|---------|--------|------|-------------|
| SMS Spam Collection | UCI | 5,572 messages | Text messages labeled ham/spam |
| Enron Email Dataset | Enron | 33,716 emails | Real company emails labeled ham/spam |
| Phishing Validation Emails | Zenodo | 2,000 emails | Safe vs phishing emails (balanced) |

**Total combined: ~41,300 messages**

## Methodology

1. **Data Cleaning** – Remove empty messages, convert to lowercase, strip whitespace
2. **TF-IDF Vectorization** – Convert text to numerical features (5000 most important words)
3. **Model Training** – Compare 4 classifiers:
   - Naive Bayes
   - Logistic Regression
   - Linear SVM
   - Random Forest
4. **Evaluation** – Accuracy, Precision, Recall, F1 Score, ROC-AUC

## Results

**Best Model: Logistic Regression**

| Metric | Score |
|--------|-------|
| Accuracy | 97.2% |
| Precision | 98.5% |
| Recall | 95.1% |
| F1 Score | 96.8% |
| ROC-AUC | 0.99 |

## Live Demo

The notebook includes an interactive widget. Type any message and get an instant prediction with confidence score.

**Example:**
Input: "Hey, I lost my phone. Can you send me your bank account info?"
Output: 🔴 SPAM or PHISHING (confidence: 94%)


## How to Run

1. Click the Colab link below (or download ipynb file)
2. Run all cells in order (Cell 1 → Cell 10)
3. Test the demo widget at the end

**Colab Link**
https://colab.research.google.com/drive/1wygWShQeU3EWqh-B009uRrAmtkYKGxHY?usp=sharing


## Repository Structure

```
spam-phishing-detection-nlp/
├── spam_phishing_detection.ipynb # Main notebook with all code
├── requirements.txt # Python dependencies
├── README.md # This file
├── LICENSE # MIT License
└── .gitignore # Files to ignore
```


## Tech Stack

- Python 3.12
- Pandas – Data manipulation
- NumPy – Numerical operations
- Scikit-learn – TF-IDF, ML models, metrics
- Matplotlib – ROC curves
- IPywidgets – Interactive demo

## Limitations

- English language only
- Does not analyze links or attachments
- May misclassify very short messages

## Future Work

- Add URL scanning for phishing links
- Use BERT or other transformers for better accuracy
- Support multiple languages
- Deploy as a web app (Streamlit or Flask)

## Author

Annel Daza COM 465 Artificial Intelligence, Spring 2026  
Instructor: Dr. Salman Sadiq Shuvo

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.
