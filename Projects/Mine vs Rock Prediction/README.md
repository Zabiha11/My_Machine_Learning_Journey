# SONAR: Rock vs Mine Prediction

> **Modern, compact README for a simple ML classification project**

---

## Project overview

This project classifies underwater sonar signals as **Rock** (R) or **Mine** (M) using a Logistic Regression classifier. It's a clean, reproducible demo of an end-to-end ML workflow: data ingestion → preprocessing → train/test split → model training → evaluation → simple predictive interface.

Nice for: interviews, portfolio pieces, quick prototyping, and learning classification basics with real-world-feeling signal data.

---

## Why this project rocks (and why it matters)

- Uses a classic binary classification dataset (Sonar). Great for benchmarking and education.
- Lightweight model (Logistic Regression) that trains fast and is interpretable.
- Includes a runnable predictive system so you can plug in new samples and get immediate predictions.
- Clean notebook that documents each step — perfect for walkthroughs or screencasts.

---

## Built with

- Python 3.8+
- NumPy
- pandas
- scikit-learn
- Jupyter Notebook

> Add virtualenv / conda as you like — instructions below.

---

## Repository structure

```
├── SONAR_Rock_vs_Mine_Prediction.ipynb   # Main notebook (step-by-step)
├── data/                                  # (optional) put sonar_data.csv here
├── models/                                # (optional) save exported models here
├── README.md                              # <-- you (this file)
```

Dataset link: https://drive.google.com/file/d/1pQxtljlNVh0DHYg-Ye7dtpDTlFceHVfa/view
---

## Quickstart — run locally

1. Clone repo

```bash
git clone <repo-url>
cd <repo>
```

2. Create environment & install deps

```bash
python -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate         # Windows
pip install -r requirements.txt
# or
pip install numpy pandas scikit-learn jupyter
```

3. Add the dataset

- Place `sonar_data.csv` in `data/` or update the notebook path. The original notebook reads `/content/sonar_data.csv` — change as needed.

4. Launch the notebook

```bash
jupyter notebook SONAR_Rock_vs_Mine_Prediction.ipynb
```

Open the notebook and run cells top → bottom. The notebook trains a Logistic Regression model and prints accuracy on training and test sets.

---

## Step-by-step walkthrough (what the notebook does)

1. **Data loading** — reads `sonar_data.csv` into a pandas DataFrame. Columns are numeric sonar returns and a final label column (`R` or `M`).

2. **Exploratory checks** — basic shape, label distribution, and sanity checks for missing values.

3. **Prepare features & labels** —
   - `X` contains the numeric sonar features.
   - `Y` contains the target labels mapped to `R` / `M`.

4. **Train/test split** — uses `train_test_split` with `test_size=0.1`, `stratify=Y`, and a fixed `random_state` for reproducibility.

5. **Model training** — trains `sklearn.linear_model.LogisticRegression()` on the training data.

6. **Evaluation** — computes accuracy on train and test sets using `accuracy_score`. The notebook prints:
   - `Accuracy on Training Data`
   - `Accuracy on Test Data`

7. **Predictive wrapper** — demonstrates converting a single sample to the required shape and running `model.predict(...)` to return `R` or `M`.

---

## How to use the predictive system (example)

Inside the notebook you'll find the pattern used to do a single prediction. In plain terms:

```python
# sample is a 1D list/array of 60 numeric sonar readings
import numpy as np
input_data = np.array(sample)
input_data_reshaped = input_data.reshape(1, -1)  # shape = (1, 60)
prediction = model.predict(input_data_reshaped)
label = 'Mine' if prediction[0] == 'M' else 'Rock'
print(label)
```

---

## Tips & next-level improvements

If you want to bump performance and make this project production-grade, consider:

- **Feature scaling** — try `StandardScaler` or `MinMaxScaler`.
- **Model tuning** — use `GridSearchCV` or `RandomizedSearchCV` to tune regularization (C) for LogisticRegression, or try SVM / RandomForest / XGBoost.
- **Cross-validation** — replace a single split with k-fold CV for robust estimates.
- **Model persistence** — save the trained model with `joblib` / `pickle` and add a small CLI or Flask/FastAPI wrapper.
- **Unit tests** — add tests for the predictive wrapper and data-loading code.
- **CI/CD** — add GitHub Actions to run tests and linting.

---

## Reproducibility checklist

- Use `random_state` everywhere (train/test split and grid search) so results are stable.
- Record package versions in `requirements.txt` or `environment.yml`.
- Keep a copy of the raw dataset used for experiments in `data/raw/`.

---

## License & contact

MIT License — use it, remix it, flex it.

Questions / collab / critique — open an issue or ping the maintainer.

---

*Made with 🔬, ☕, and a little bit of hustle.*

