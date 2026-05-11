# Visualization Techniques in ML — AWS AI Practitioner Exam (Pinoy Version) 🇵🇭

Mga visualization tools at techniques na ginagamit sa Machine Learning pipeline.

---

## 🎯 Bakit Important ang Visualization sa ML?

**Pinoy analogy:** Parang **X-ray ng katawan** — hindi mo makikita ang problema kung hindi mo i-visualize. Sa ML, visualization helps you understand data, detect problems, at evaluate model performance.

---

## 📊 Data Exploration Visualizations

---

### 1. Scatter Plot

**Ano to:** Dots sa graph na nagpapakita ng **relationship between 2 variables**.

**Pinoy analogy:** Parang **mapa ng mga bahay** — bawat dot ay isang data point, at nakikita mo kung may pattern (clustered ba? linear ba?).

**Ginagamit para sa:**
- See correlations between features
- Identify clusters/groups
- Spot outliers

```
Y │    •  •
  │  •  •  •
  │ • •  •
  │• •
  └──────────── X
```

---

### 2. Histogram

**Ano to:** Bar chart na nagpapakita ng **distribution/frequency** ng isang variable.

**Pinoy analogy:** Parang **survey results** — "ilan ang may grade 90-95? ilan ang 85-90?" Nakikita mo kung saan concentrated ang data.

**Ginagamit para sa:**
- Understand data distribution (normal? skewed?)
- Detect imbalanced classes
- Identify outliers

---

### 3. Box Plot (Box and Whisker)

**Ano to:** Shows **median, quartiles, at outliers** ng data in one compact visual.

**Pinoy analogy:** Parang **summary ng exam scores ng buong class** — nakikita mo yung average, yung range, at yung mga outliers (sobrang taas o baba).

**What each part means:**

```
        Outlier
          •
    ┬─────────┬  ← Maximum (excluding outliers)
    │         │
    │    ─────│  ← Q3 (75th percentile)
    │    │    │
    │    ─────│  ← Median (50th)
    │    │    │
    │    ─────│  ← Q1 (25th percentile)
    │         │
    ┴─────────┴  ← Minimum
          •
        Outlier
```

**Ginagamit para sa:**
- Compare distributions across groups
- Spot outliers quickly
- See data spread and skewness

---

### 4. Heatmap / Correlation Matrix

**Ano to:** Color-coded grid na nagpapakita ng **strength of relationships** between all feature pairs.

**Pinoy analogy:** Parang **seating chart na color-coded** — red = magkaaway, green = magkaibigan. Nakikita mo agad kung sino ang related.

**Ginagamit para sa:**
- Identify highly correlated features (multicollinearity)
- Feature selection — remove redundant features
- Understand feature relationships

```
         Age  Income  Spend
Age      1.0   0.7    0.3
Income   0.7   1.0    0.9   ← High correlation!
Spend    0.3   0.9    1.0
```

---

### 5. Pair Plot

**Ano to:** Grid of scatter plots — **every feature vs every other feature** in one view.

**Pinoy analogy:** Parang **class photo na lahat naka-pair** — nakikita mo lahat ng possible combinations at relationships.

**Ginagamit para sa:**
- Quick overview ng all feature relationships
- Identify which features separate classes well
- Spot patterns across multiple dimensions

---

## 📈 Model Performance Visualizations

---

### 6. Confusion Matrix

**Ano to:** Table na nagpapakita ng **correct vs incorrect predictions** per class.

**Pinoy analogy:** Parang **scorecard ng referee** — ilan ang tama, ilan ang mali, at anong klaseng mali (false positive vs false negative).

```
                 Predicted
              Positive  Negative
Actual  Pos │   TP    │   FN    │  ← Missed (Type II error)
        Neg │   FP    │   TN    │  ← False alarm (Type I error)
```

**Ginagamit para sa:**
- See exactly where model makes mistakes
- Calculate precision, recall, F1
- Identify which classes are confused with each other

---

### 7. ROC Curve (Receiver Operating Characteristic)

**Ano to:** Graph ng **True Positive Rate vs False Positive Rate** at different thresholds.

**Pinoy analogy:** Parang **trade-off chart** — "Kung gusto kong mahuli lahat ng magnanakaw (high recall), gaano karaming innocent ang maa-accuse ko (high FPR)?"

```
TPR │      ___________
    │    /
    │   /
    │  /    ← Good model (curves toward top-left)
    │ /
    │/______________ FPR
```

**Key concepts:**
- **AUC (Area Under Curve)** — 1.0 = perfect, 0.5 = random guess
- Closer to top-left corner = better model
- Diagonal line = random classifier (useless)

**Ginagamit para sa:**
- Compare multiple models
- Choose optimal threshold
- Evaluate binary classifiers

---

### 8. Precision-Recall Curve

**Ano to:** Graph ng **Precision vs Recall** at different thresholds — better than ROC for imbalanced datasets.

**Pinoy analogy:** Parang **balancing act** — "Gusto kong mahuli lahat ng fraud (recall), pero ayoko namang mag-false alarm sa innocent (precision)."

**Ginagamit para sa:**
- Imbalanced datasets (e.g., 1% fraud, 99% legit)
- When false positives and false negatives have different costs
- Choosing threshold for specific business needs

---

### 9. Learning Curve

**Ano to:** Graph ng **model performance vs training data size** — shows if model benefits from more data.

**Pinoy analogy:** Parang **progress chart ng student** — "Habang dumadami ang practice exams, tumataas ba ang score? O nag-p-plateau na?"

```
Score │    ___________  ← Training score
      │   /
      │  /   _________  ← Validation score
      │ /  /
      │/ /
      └──────────────── Training data size
```

**What it tells you:**

| Pattern | Meaning |
|---------|---------|
| Both scores high, close together | Good fit ✅ |
| Training high, validation low | Overfitting 🔴 |
| Both scores low | Underfitting 🔴 (need better model) |
| Gap closing with more data | More data will help |

---

### 10. Loss Curve (Training/Validation Loss)

**Ano to:** Graph ng **error (loss) over training epochs** — shows if model is learning properly.

**Pinoy analogy:** Parang **weight loss chart** — dapat bumababa over time. Pag tumataas ulit, may problema.

```
Loss │\
     │ \  ← Training loss
     │  \    /── Validation loss starts increasing = OVERFITTING
     │   \ /
     │    X
     │     \___
     └──────────── Epochs
```

**What to look for:**

| Pattern | Meaning |
|---------|---------|
| Both decreasing | Model is learning ✅ |
| Training decreases, validation increases | Overfitting 🔴 |
| Both stay high | Underfitting 🔴 |
| Both plateau | Model converged (stop training) |

---

## 🔍 Model Explainability Visualizations

---

### 11. Feature Importance Plot

**Ano to:** Bar chart na nagpapakita kung **anong features ang pinaka-influential** sa model predictions.

**Pinoy analogy:** Parang **ranking ng factors** — "Ano ang pinaka-important sa pagpili ng bahay? Location #1, Price #2, Size #3..."

```
Income     ████████████  0.45
Age        ████████      0.30
Location   █████         0.15
Gender     ███           0.10
```

**Ginagamit para sa:**
- Understand what drives predictions
- Feature selection (remove unimportant ones)
- Detect if model uses biased features

**AWS:** SageMaker Clarify provides SHAP-based feature importance

---

### 12. SHAP (SHapley Additive exPlanations) Values

**Ano to:** Shows **how each feature contributes** to a specific prediction — positive (pushes toward positive) or negative (pushes toward negative).

**Pinoy analogy:** Parang **breakdown ng exam score** — "Nakuha mo 85 kasi: +10 sa math, +5 sa science, -3 sa english, +3 sa history..."

```
Base value: 50% (average prediction)

Income = High     → +20%  (pushes toward approval)
Age = 25          → -5%   (slightly against)
Credit Score = 750 → +15% (pushes toward approval)
Employment = New  → -10%  (against)

Final prediction: 70% (approved)
```

**Ginagamit para sa:**
- Individual prediction explanations
- Regulatory compliance (explain decisions)
- Bias detection

**Exam tip:** "Why did model predict X for this specific customer?" → **SHAP values**

---

### 13. t-SNE / UMAP (Dimensionality Reduction Visualization)

**Ano to:** Converts high-dimensional data (100+ features) into **2D/3D plot** na pwedeng i-visualize.

**Pinoy analogy:** Parang **world map** — yung Earth is 3D, pero ni-flatten mo into 2D para makita mo lahat. May distortion, pero useful pa rin.

**Ginagamit para sa:**
- Visualize clusters in high-dimensional data
- Check if embeddings make sense
- Verify that similar items are grouped together

---

## 📉 Overfitting vs Underfitting (Visual Diagnosis)

| | Underfitting | Good Fit | Overfitting |
|--|---|---|---|
| **Visual** | Too simple — misses pattern | Captures pattern | Too complex — memorizes noise |
| **Training score** | Low | High | Very high |
| **Validation score** | Low | High (close to training) | Low (far from training) |
| **Pinoy analogy** | Student na hindi nag-aral | Student na nag-review well | Student na nag-memorize ng answers pero di naintindihan |

**How to fix:**

| Problem | Solutions |
|---------|-----------|
| Underfitting | More complex model, more features, less regularization |
| Overfitting | More data, regularization, dropout, simpler model, early stopping |

---

## 🎯 Summary Table

| Visualization | Para saan | Kailan gamitin |
|---------------|-----------|----------------|
| Scatter Plot | Relationship between 2 variables | Data exploration, correlation |
| Histogram | Distribution of one variable | Check data balance, outliers |
| Box Plot | Summary statistics + outliers | Compare groups, spot outliers |
| Heatmap | Correlation between all features | Feature selection |
| Confusion Matrix | Classification errors breakdown | Evaluate classifier |
| ROC Curve | TPR vs FPR trade-off | Compare models, choose threshold |
| Precision-Recall Curve | Precision vs Recall trade-off | Imbalanced datasets |
| Learning Curve | Performance vs data size | Need more data? |
| Loss Curve | Error over training time | Overfitting detection |
| Feature Importance | Which features matter most | Explainability, feature selection |
| SHAP Values | Per-prediction explanation | Individual explanations, bias |
| t-SNE/UMAP | High-dimensional data in 2D | Cluster visualization |

---

## 📝 Exam-Style Questions

| Kung ang tanong ay about... | Sagot |
|-----------------------------|-------|
| Visualizing model errors per class | Confusion Matrix |
| Comparing classifiers overall performance | ROC Curve / AUC |
| Explaining individual predictions | SHAP Values |
| Detecting overfitting during training | Loss Curve (training vs validation) |
| Finding which features are most important | Feature Importance Plot |
| Evaluating on imbalanced data | Precision-Recall Curve |
| Visualizing high-dimensional clusters | t-SNE / UMAP |
| Checking data distribution | Histogram / Box Plot |
| Finding correlated features | Heatmap / Correlation Matrix |

---

**Bottom line para sa exam:** Confusion Matrix (classification errors), ROC/AUC (model comparison), SHAP (explainability), at Loss Curve (overfitting detection) — yan ang madalas i-tanong. 🎯
