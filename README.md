# 🔍 Fake News Detection

A machine learning project that classifies news articles as **fake** or **real** using Natural Language Processing (NLP) and text classification techniques.

---

## 📋 Problem Statement

Misinformation spreads rapidly across social media and news platforms, causing confusion, affecting public opinion, and damaging trust in news outlets. This project aims to **automatically detect fake news articles** using machine learning models trained on labeled news data.

### Why it matters:
- ✅ Helps combat misinformation
- ✅ Improves media literacy
- ✅ Supports fact-checking automation
- ✅ Protects users from misleading content

---

## 🎯 Project Overview

This project implements a complete machine learning pipeline:

1. **Data Loading** – Reads news articles from separate CSV files (`Fake.csv`, `True.csv`)
2. **Data Preprocessing** – Cleans text, removes stopwords, handles missing values
3. **Feature Extraction** – Converts text to numerical features (TF-IDF)
4. **Model Training** – Trains classification models (Logistic Regression, etc.)
5. **Evaluation** – Tests accuracy, precision, recall, F1-score
6. **Prediction** – Classifies new articles as fake or real

---

## 📁 Project Structure

```
fake_news_detection/
├── data/
│   ├── Fake.csv              # Fake/unreliable news articles (label = 1)
│   ├── True.csv              # Real/reliable news articles (label = 0)
│   └── news.csv              # Test dataset for evaluation
├── fake_news_detection.ipynb # Main code notebook
├── requirements.txt          # Python dependencies
├── LICENSE                   # License file
└── README.md                 # This file
```

---

## 📊 Dataset Structure

Your project uses **three CSV files** instead of a single training file:

### Files in `data/` folder:

| File | Content | Label | Purpose |
|------|---------|-------|---------|
| **Fake.csv** | Unreliable/fake articles | 1 | Training (fake class) |
| **True.csv** | Reliable/real articles | 0 | Training (real class) |
| **news.csv** | Mixed articles | - | Testing/Validation |

### Expected Columns in Each CSV:

Each CSV file should have these columns:

```
title       - Article headline/title
author      - Author name (can be empty)
text        - Full article text
```

### Example data:

```csv
title,author,text
COVID-19 Vaccine Safety Confirmed,Dr. Smith,"Studies show vaccines are safe and effective..."
Fake Vaccine Causes Mutations,Unknown,"Unproven claims about vaccines causing mutations..."
```

---

## 🚀 Quick Start (5 minutes)

### Prerequisites
- Python 3.7 or higher
- pip (Python package manager)
- Git

### Step 1: Clone the repository
```bash
git clone https://github.com/Nimmanagotitharunkumarhello/fake_news_detection.git
cd fake_news_detection
```

### Step 2: Create a virtual environment (recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python -m venv venv
source venv/bin/activate
```

### Step 3: Install dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Verify data files are in place

Make sure all three CSV files exist in the `data/` folder:

```bash
# Windows
dir data\

# Linux/Mac
ls data/
```

You should see:
- ✅ `Fake.csv`
- ✅ `True.csv`
- ✅ `news.csv`

### Step 5: Run the project

```bash
jupyter notebook
```

Then:
- Open `fake_news_detection.ipynb`
- Run all cells in order (Shift + Enter)
- The notebook will automatically:
  - Load `Fake.csv` → Label = 1
  - Load `True.csv` → Label = 0
  - Combine them into a training dataset
  - Train and evaluate the model
  - Test on `news.csv`

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| **Python 3.7+** | Programming language |
| **Pandas** | Data manipulation and loading |
| **NumPy** | Numerical computations |
| **Scikit-learn** | Machine learning models and metrics |
| **TF-IDF** | Text feature extraction |
| **Jupyter Notebook** | Interactive development environment |
| **NLTK** | Natural language processing (if used) |

---

## 📈 Model Pipeline

```
Fake.csv + True.csv (with labels)
     ↓
Text Preprocessing (cleaning, tokenization)
     ↓
Feature Extraction (TF-IDF vectorization)
     ↓
Train/Test Split
     ↓
Model Training (Logistic Regression / SVM)
     ↓
Model Evaluation (Accuracy, Precision, Recall, F1)
     ↓
Predictions on news.csv
```

---

## 📊 Expected Results

Once your model is trained on your dataset, you should see:

- **Accuracy**: 90%+ (depends on data quality)
- **Precision**: How many predicted fake articles are actually fake
- **Recall**: How many actual fake articles were correctly identified
- **F1-Score**: Balanced measure between precision and recall

Example output:
```
Model Performance:
- Accuracy: 94.5%
- Precision: 93.2%
- Recall: 95.8%
- F1-Score: 94.5%
```

---

## 💡 Key Features

✅ **Automated text preprocessing** – Removes noise and normalizes text  
✅ **Separate training files** – Easy to manage fake vs real articles separately  
✅ **Multiple classifiers** – Compare different ML models  
✅ **Performance metrics** – Detailed evaluation with confusion matrix  
✅ **Easy to use** – Just run the notebook, no complex setup  
✅ **Scalable** – Works with datasets of any size (adjust sample size if needed)  

---

## 🔮 Future Enhancements

- [ ] Implement deep learning models (LSTM, BERT, Transformers)
- [ ] Add web interface (Flask/Streamlit)
- [ ] Deploy as a REST API
- [ ] Real-time fact-checking with external APIs
- [ ] Support for multiple languages
- [ ] Interactive visualization dashboard
- [ ] Model optimization and hyperparameter tuning

---

## 🤝 Contributing

Found a bug or have an improvement idea? Feel free to:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add your message'`)
5. Push to the branch (`git push origin feature/your-feature`)
6. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License – see the **LICENSE** file for details.

---

## 📞 Support & Troubleshooting

### Common Issues:

**"FileNotFoundError: data/Fake.csv not found"**
- Solution: Make sure all 3 CSV files are in the `data/` folder
- Check file names are exactly: `Fake.csv`, `True.csv`, `news.csv` (case-sensitive)

**"Column 'title' not found"**
- Solution: Open your CSV files in Excel to verify column names
- Ensure columns are: `title`, `author`, `text`
- Update code if column names are different

**"UnicodeDecodeError" or encoding errors**
- Solution: Specify encoding when reading CSV:
  ```python
  pd.read_csv("data/Fake.csv", encoding='latin-1')
  ```

**Model takes too long to train**
- Solution: Load only sample of data:
  ```python
  fake_df = pd.read_csv("data/Fake.csv", nrows=5000)
  true_df = pd.read_csv("data/True.csv", nrows=5000)
  ```

For more detailed data setup instructions, see **DATA_GUIDE.md**

---

## 👤 Author

**Nimmanagotitharunkumarhello**  
GitHub: https://github.com/Nimmanagotitharunkumarhello

---

## 🎓 Learning Resources

- [Scikit-learn documentation](https://scikit-learn.org/)
- [TF-IDF explanation](https://en.wikipedia.org/wiki/Tf%E2%80%93idf)
- [NLP with Python](https://www.nltk.org/)
- [Kaggle Fake News datasets](https://www.kaggle.com/datasets)
- [Machine Learning Basics](https://developers.google.com/machine-learning/crash-course)

---

## ⭐ Show your support

If you found this project helpful, please give it a **star** ⭐ on GitHub!

---

**Last Updated:** January 3, 2026  
**Status:** ✅ Ready to use  
**Data:** ✅ All files included in `data/` folder
