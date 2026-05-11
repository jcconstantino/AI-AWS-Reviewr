# AI/ML Evaluation Metrics — AWS AI Practitioner Exam (Pinoy Version) 🇵🇭

Mga metrics na ginagamit para sukatin kung **gaano kagaling** ang AI/ML model mo.

---

## 📊 Classification Metrics (Para sa Models na Nag-p-predict ng Category)

---

### F1 Score

**Ano to:** Yung **balance between Precision at Recall** — single number na nagsasabi kung overall magaling ba ang model mo sa classification.

**Pinoy analogy:** Parang **grade sa exam na may partial credit** — hindi lang "ilan ang tama" (precision), kundi "ilan sa lahat ng dapat tamang nasagot mo" (recall). F1 = average ng dalawa.

**Formula:** F1 = 2 × (Precision × Recall) / (Precision + Recall)

**Kailangan muna maintindihan:**

| Metric | Meaning | Pinoy Analogy |
|--------|---------|---------------|
| Precision | Sa lahat ng sinabi mong "positive," ilan ang talagang positive? | "Sa lahat ng inakusahan mong magnanakaw, ilan ang talagang magnanakaw?" |
| Recall | Sa lahat ng talagang positive, ilan ang na-detect mo? | "Sa lahat ng totoong magnanakaw, ilan ang nahuli mo?" |
| F1 Score | Harmonic mean ng Precision at Recall | "Overall, gaano ka kagaling — hindi mo na-miss, at hindi ka rin nag-false alarm?" |

**Confusion Matrix:**

```
                    Predicted Positive    Predicted Negative
Actual Positive     True Positive (TP)    False Negative (FN) ← "na-miss"
Actual Negative     False Positive (FP)   True Negative (TN)
                    ↑ "false alarm"
```

**Kailan important:**
- Imbalanced datasets (e.g., 99% not fraud, 1% fraud)
- When both false positives AND false negatives matter
- Medical diagnosis, fraud detection, spam filtering

**Exam tip:** Pag ang tanong ay "balanced measure of model performance" → **F1 Score**

---

### Other Classification Metrics (Quick Reference)

| Metric | Formula | Kailan gamitin |
|--------|---------|----------------|
| Accuracy | (TP + TN) / Total | Balanced datasets only |
| Precision | TP / (TP + FP) | When false alarms are costly (spam filter) |
| Recall (Sensitivity) | TP / (TP + FN) | When missing positives is costly (cancer detection) |
| Specificity | TN / (TN + FP) | When false positives on negatives matter |
| AUC-ROC | Area under ROC curve | Overall model discrimination ability |

---

## 📝 Text Generation Metrics (Para sa GenAI/NLP Models)

---

### ROUGE (Recall-Oriented Understudy for Gisting Evaluation)

**Ano to:** Measures quality of **text summarization** — comparing generated summary vs reference (human-written) summary.

**Pinoy analogy:** Parang **teacher na nag-c-check ng book report** — "Gaano karami sa important points ng libro ang nasama sa summary mo?"

**Focus:** RECALL-oriented — "Gaano karami sa reference ang na-capture ng generated text?"

**Types:**

| Type | Ano chine-check |
|------|-----------------|
| ROUGE-1 | Overlap ng individual words (unigrams) |
| ROUGE-2 | Overlap ng word pairs (bigrams) |
| ROUGE-L | Longest common subsequence (sentence structure) |
| ROUGE-S | Skip-bigram (word pairs na pwedeng may gap) |

**Example:**

```
Reference: "The cat sat on the mat"
Generated: "The cat is on the mat"

ROUGE-1: 5 matching words out of 6 in reference = 0.83 recall
```

**Kailan gamitin:** Evaluating summarization models

**Exam tip:** Summarization quality → **ROUGE**. "R" in ROUGE = Recall-oriented.

---

### BLEU (Bilingual Evaluation Understudy)

**Ano to:** Measures quality of **machine translation** — comparing generated translation vs reference (human) translation.

**Pinoy analogy:** Parang **language teacher na nag-g-grade ng translation homework** — "Gaano ka-close yung translation mo sa correct answer?"

**Focus:** PRECISION-oriented — "Gaano karami sa generated text ang tama based sa reference?"

**How it works:**

| Component | Ano ginagawa |
|-----------|--------------|
| n-gram precision | Checks 1-gram, 2-gram, 3-gram, 4-gram overlap |
| Brevity penalty | Penalizes kung masyadong maikli ang translation |
| Score range | 0 to 1 (1 = perfect match with reference) |

**Example:**

```
Reference: "The cat is on the mat"
Generated: "The the the the"

BLEU penalizes this — kahit "the" appears in reference, 
hindi pwedeng ulit-ulit lang.
```

**Kailan gamitin:** Evaluating translation models

**Exam tip:** Translation quality → **BLEU**. "B" in BLEU = Bilingual.

---

### ROUGE vs BLEU — Key Difference

| | ROUGE | BLEU |
|--|-------|------|
| **Measures** | Summarization quality | Translation quality |
| **Focus** | Recall (gaano karami sa reference ang na-capture?) | Precision (gaano karami sa generated ang tama?) |
| **Question** | "Na-cover mo ba lahat ng important points?" | "Tama ba yung mga words na ginamit mo?" |
| **Pinoy analogy** | "Kumpleto ba yung book report mo?" | "Tama ba yung grammar at word choice ng translation mo?" |

---

## 😊 Business/Application Metrics

---

### Customer Satisfaction Score (CSAT)

**Ano to:** Measures kung **satisfied ba ang users** sa AI system output — typically through surveys or ratings after interaction.

**Pinoy analogy:** Parang **"Rate your experience 1-5 stars"** sa Grab or Foodpanda after delivery.

**How it works:**

| Aspect | Details |
|--------|---------|
| Collection method | Post-interaction survey ("Was this helpful? 👍👎") |
| Scale | Usually 1-5 stars, or thumbs up/down |
| Formula | (Satisfied responses / Total responses) × 100% |
| Target | Typically 80%+ is good |

**Kailan gamitin:**
- Evaluating chatbots and virtual assistants
- Measuring AI-powered customer service quality
- Bedrock-powered Q&A systems
- Any user-facing AI application

**What it captures that technical metrics don't:**

| Technical Metrics (ROUGE, BLEU, F1) | CSAT |
|--------------------------------------|------|
| "Technically correct ba ang output?" | "Happy ba ang user sa output?" |
| Objective, automated | Subjective, human feedback |
| Measures model quality | Measures user experience |

**Exam tip:** Pag ang tanong ay about measuring **end-user happiness** with AI system → **CSAT**

---

## 🔢 Regression Metrics (Para sa Models na Nag-p-predict ng Numbers)

| Metric | Ano sinusukat | Pinoy Analogy |
|--------|---------------|---------------|
| MAE (Mean Absolute Error) | Average na layo ng prediction sa actual | "On average, gaano kalayo ang hula mo?" |
| MSE (Mean Squared Error) | Average ng squared errors — penalizes big mistakes more | "Mas mabigat ang penalty pag malayo ang miss" |
| RMSE (Root MSE) | Square root ng MSE — same unit as target | "MAE pero mas strict sa big errors" |
| R² (R-squared) | Percentage ng variance explained by model (0-1) | "Gaano ka-good ang model mo vs random guess?" |

---

## 🤖 GenAI-Specific Metrics

| Metric | Ano sinusukat |
|--------|---------------|
| Perplexity | How "surprised" the model is by text — lower = better |
| BERTScore | Semantic similarity using BERT embeddings |
| Human Evaluation | Humans rate fluency, relevance, correctness |
| Groundedness | Are responses supported by provided context? (for RAG) |
| Toxicity Score | How harmful/offensive is the output? |
| Hallucination Rate | Percentage of responses with fabricated info |

---

## 🎯 Master Summary — When to Use What

| Kung ang task ay... | Metric na gamitin |
|---------------------|-------------------|
| Text summarization | ROUGE |
| Machine translation | BLEU |
| Classification (balanced) | Accuracy, F1 |
| Classification (imbalanced) | F1, Precision, Recall, AUC-ROC |
| Predicting numbers | MAE, RMSE, R² |
| User satisfaction with AI | CSAT |
| Overall GenAI text quality | BERTScore, Human Evaluation |
| Chatbot/assistant quality | CSAT + Human Evaluation |
| RAG accuracy | Groundedness + ROUGE |
| Content safety | Toxicity Score |

---

## 📝 Exam-Style Questions

| Kung ang tanong ay about... | Sagot |
|-----------------------------|-------|
| Measuring summarization quality | ROUGE |
| Measuring translation quality | BLEU |
| Balance of precision and recall | F1 Score |
| Recall-oriented text evaluation | ROUGE (R = Recall) |
| Precision-oriented text evaluation | BLEU |
| End-user happiness with AI chatbot | CSAT |
| Model performance on imbalanced data | F1 Score (not accuracy!) |
| How "surprised" a language model is | Perplexity |
| Semantic similarity of generated text | BERTScore |

---

**Bottom line para sa exam:**
- **Summarization** → ROUGE (Recall-focused)
- **Translation** → BLEU (Precision-focused)
- **Classification** → F1 Score (Precision + Recall balance)
- **User experience** → CSAT (satisfaction rating)

Alam mo yang apat = covered ka na. 🎯
