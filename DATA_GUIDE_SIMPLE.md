# 📦 Data Setup Guide (Quick Version)

Your project is **already set up!** ✅

---

## 📁 Your Current Structure

```
fake_news_detection/
├── data/
│   ├── Fake.csv       ✅ Fake articles (label = 1)
│   ├── True.csv       ✅ Real articles (label = 0)
│   └── news.csv       ✅ Test dataset
├── fake_news_detection.ipynb
├── LICENSE
└── README.md
```

---

## 🚀 How to Run

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Open Jupyter:**
   ```bash
   jupyter notebook
   ```

3. **Run the notebook:**
   - Open `fake_news_detection.ipynb`
   - Click "Run All" or press `Shift + Enter` to run each cell
   - The code automatically loads `Fake.csv`, `True.csv`, and `news.csv`

---

## 📊 Your Data Files

| File | Content | Label |
|------|---------|-------|
| `Fake.csv` | Articles that are fake/unreliable | 1 |
| `True.csv` | Articles that are real/reliable | 0 |
| `news.csv` | Test or validation data | - |

Your notebook will:
1. Load and combine `Fake.csv` + `True.csv`
2. Train a model to classify fake vs real news
3. Test on `news.csv`

---

## ✅ Pre-Run Checklist

- [ ] All 3 CSV files are in the `data/` folder
- [ ] Python and Jupyter Notebook installed
- [ ] Dependencies installed: `pip install -r requirements.txt`
- [ ] CSV files have columns: `title`, `author`, `text`

---

## ❓ If You Get Errors

**"FileNotFoundError: data/Fake.csv not found"**
- Verify the file exists: Right-click project folder → Open in Terminal → Type: `ls data/` (Mac/Linux) or `dir data` (Windows)

**"Column 'title' not found"**
- Open CSV in Excel to see actual column names
- Update code if column names are different

**"UnicodeDecodeError"**
- Add encoding to CSV read: `pd.read_csv("data/Fake.csv", encoding='latin-1')`

---

## 🎯 That's It!

Your project is ready. No need to download datasets—you already have them! 🎉

Just run the notebook and see your results!
