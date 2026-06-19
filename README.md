<<<<<<< HEAD
# 🎓 Student Performance Prediction

A complete Machine Learning project that predicts student academic performance
using **attendance**, **assignment scores**, and **exam marks** — with both a
CLI pipeline and a Flask web app (live predictor + analytics dashboard).

---

## 📁 Project Structure

```
student_performance/
├── data/
│   ├── generate_data.py        # Synthetic dataset generator (500 students)
│   ├── student_data.csv        # Generated after run_all.py
│   └── __init__.py
├── models/                     # Saved model artefacts (after training)
│   ├── best_model.pkl
│   ├── scaler.pkl
│   ├── label_encoder.pkl
│   ├── features.pkl
│   ├── all_results.pkl
│   └── eval_data.pkl
├── charts/                     # 6 PNG visualisations (after run)
├── reports/
│   └── report.html             # Full HTML report (after run)
├── templates/                  # Flask web UI
│   ├── index.html              # Predictor page
│   └── dashboard.html          # Analytics dashboard
├── app.py                      # Flask web app (predictor + dashboard)
├── train_model.py              # ML training – 4 models compared
├── visualize.py                # Chart generation (6 charts)
├── predict.py                  # Prediction CLI
├── generate_report.py          # HTML report generator
├── run_all.py                  # One-shot pipeline (train → charts → report)
└── requirements.txt
```

---

## 🚀 Quick Start

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Run the full ML pipeline
```bash
python run_all.py
```
This will:
- Generate a 500-student synthetic dataset
- Train & compare 4 ML models
- Produce 6 charts in `charts/`
- Generate `reports/report.html`
- Show sample predictions

### 3. Launch the web app
```bash
python app.py
```
Then visit **http://localhost:5000**

| Route | Description |
|---|---|
| `/` | Predictor — enter a student's stats and get an instant prediction |
| `/predict` | `POST` endpoint used by the predictor page (JSON in, JSON out) |
| `/dashboard` | Dataset stats, model comparison table, and all 6 charts |

> ⚠️ The web app reads the artefacts in `models/` and `charts/`, so run
> `python run_all.py` at least once before starting `app.py`.

### 4. Predict from the CLI (optional)
```bash
python predict.py                # sample students
python predict.py --interactive  # enter values manually
```

---

## 📊 Features Used

| Feature | Description |
|---|---|
| `attendance_pct` | Percentage of classes attended (0–100) |
| `assignment1–5` | Individual assignment scores (0–100) |
| `assignment_avg` | Mean of all 5 assignments |
| `midterm_score` | Mid-semester exam score (0–100) |
| `final_exam_score` | Final exam score (0–100) |

**Target:** `performance` → **Good** / **Average** / **Poor**

---

## 🤖 Models Compared

| Model | Notes |
|---|---|
| Random Forest | Best performer (typically ~93%) |
| Gradient Boosting | Close second |
| Logistic Regression | Fast baseline |
| SVM (RBF kernel) | Strong on small datasets |

The best model (by accuracy) is saved to `models/best_model.pkl` and is what
both `predict.py` and the Flask `/predict` route use.

---

## 📈 Charts Generated

1. Performance Distribution (bar chart)
2. Feature Correlation Heatmap
3. Attendance vs Composite Score (scatter)
4. Confusion Matrix (best model)
5. Model Accuracy & F1 Comparison
6. Score Distributions by Performance (boxplots)

All 6 are embedded directly in the `/dashboard` page, alongside total
students, performance breakdown, average attendance/score, and best model
accuracy.

---

## 🖥 Web App Preview

- **Predictor page** — sliders/inputs for attendance, 5 assignments, midterm
  and final exam, with live validation. Returns predicted performance, grade,
  confidence %, per-class probability breakdown, composite score, and
  personalised advice.
- **Dashboard page** — KPI cards, a model comparison table, and all 6 charts
  in a responsive grid.

---

## 🛠 Tech Stack

- **Python 3.8+**
- **scikit-learn** – ML models
- **pandas / numpy** – data processing
- **matplotlib / seaborn** – visualizations
- **joblib** – model persistence
- **Flask** – web app (predictor + dashboard)

---

## 📝 License

This project is provided for educational purposes. Feel free to fork, modify,
and use it as a starting point for your own ML/Flask projects.
=======
# LearnPredict
 ML-powered student performance predictor with a Flask web UI — live predictions, model comparison, and analytics dashboard.
>>>>>>> ecd7242ed15949f71e1de963c0e79ac4569b1dfb
