# 🧠 ML Password Strength Classifier

This module trains and maintains a **password strength scoring model** for your AI-Powered Password Manager. It uses `scikit-learn` for simplicity and offline compatibility.

---

## 📌 What This Model Does

- Classifies passwords into **weak**, **moderate**, or **strong**
- Trained on features like:
  - Length
  - Character variety (symbols, digits, uppercase)
  - Entropy estimation
- Exported as a `.pkl` file for live use in CLI

---

## 🗂 Folder Structure

```
ml/
├── data/
│   ├── raw/                 # Source CSV (weak vs strong)
│   └── processed/           # Cleaned dataset for training
├── models/
│   ├── password\_strength.pkl  # Final model for use
│   └── model\_meta.json        # Training info + metrics
├── utils/
│   └── preprocess.py        # Feature extraction for training & inference
├── training/
│   ├── train\_model.py       # Train the model offline
│   └── evaluate\_model.py    # View accuracy + metrics
├── logs/
│   └── training\_log.md      # Manual training session summaries

```

---

## 🚀 How to Train the Model

> Make sure you're in the root folder (`AI-Powered-Password-Manager/`):

```bash
python ml/training/train_model.py

```

This will:

* Load and preprocess data
* Train a `LogisticRegression` classifier
* Save the model to `ml/models/password_strength.pkl`
* Log accuracy, precision, recall, F1 to `training_log.md`

---

## 🧪 Evaluate the Model

To check how the model is performing:

```bash
python ml/training/evaluate_model.py
```

---

## 🔄 Live Use: Integrating with CLI

In `cli/password_utils.py`:

```python
import joblib
from ml.utils.preprocess import extract_features

# Load model once
MODEL_PATH = "ml/models/password_strength.pkl"
password_model = joblib.load(MODEL_PATH)

def score_password(password: str) -> str:
    features = extract_features(password)  # Returns list or np.array
    prediction = password_model.predict([features])[0]
    labels = {0: "Weak", 1: "Moderate", 2: "Strong"}
    return labels.get(prediction, "Unknown")
```

In `cli/main.py`:

```python
from password_utils import score_password

def check_strength():
    password = input("Enter password to test: ")
    strength = score_password(password)
    print(f"Password Strength: {strength}")
```

---

## 🛠 Requirements

* scikit-learn
* pandas
* numpy
* joblib

Install:

```bash
pip install -r requirements.txt
```

---

## ✅ Tips

* Use small datasets for initial training, then expand
* Add entropy scoring or zxcvbn-derived features if needed
* Version models as your logic improves (`v1`, `v2`, etc.)

---

## 📌 Next Steps

* Use LLM to label custom password samples in `prompts/`
* Add command to re-train model from CLI

---
