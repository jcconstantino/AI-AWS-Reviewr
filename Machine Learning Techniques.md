# Machine Learning Techniques (Pinoy Version) 🇵🇭

Ito yung mga **specific algorithms/methods** na ginagamit within each learning type:

---

## 📊 Regression (Prediction ng Numbers)

**Ano to:** Nag-p-predict ng continuous value (numero).

**Pinoy analogy:** Parang **manghuhula ng presyo** — "Based sa size, location, at age ng bahay, magkano kaya ito?"

**Techniques:**

| Technique | Pano gumagana |
|-----------|---------------|
| Linear Regression | Gumuguhit ng straight line sa data — simplest |
| Polynomial Regression | Curved line — para sa complex relationships |
| Ridge/Lasso Regression | May penalty para iwas overfitting |

**Use case:** Predict electricity bill based sa usage, predict crop yield based sa weather

---

## 🏷️ Classification (Prediction ng Category)

**Ano to:** Nag-a-assign ng label/category sa data.

**Pinoy analogy:** Parang **sorting hat sa Harry Potter** — "Ikaw, Gryffindor! Ikaw, Slytherin!"

**Techniques:**

| Technique | Pano gumagana |
|-----------|---------------|
| Logistic Regression | Yes/No decisions — spam or not spam |
| Decision Trees | Series of if-else questions — parang 20 questions game |
| Random Forest | Maraming decision trees na nag-vo-vote — majority wins |
| Support Vector Machine (SVM) | Naghahanap ng best dividing line between categories |
| K-Nearest Neighbors (KNN) | "Sino yung mga kapitbahay mo? Kung majority pusa, ikaw din pusa" |
| Naive Bayes | Probability-based — "based sa words, spam ba ito?" |

**Use case:** Email spam detection, disease diagnosis, textile defect classification

---

## 🧩 Clustering (Grouping Without Labels)

**Ano to:** Nag-g-group ng similar items together — walang predefined categories.

**Pinoy analogy:** Parang **mag-sort ng damit sa labahan** — hindi mo sinabihan kung pano, pero natural na pinaghiwalay mo yung puti, colored, at delicates.

**Techniques:**

| Technique | Pano gumagana |
|-----------|---------------|
| K-Means | "Hatiin mo sa K groups, minimize yung distance within each group" |
| Hierarchical Clustering | Tree-like structure — from individual items to big groups |
| DBSCAN | Density-based — finds clusters of any shape, ignores outliers |

**Use case:** Customer segmentation, document grouping, anomaly detection

---

## 📉 Dimensionality Reduction (Simplify ang Data)

**Ano to:** Nag-r-reduce ng number of features/columns — para mas simple at mas mabilis.

**Pinoy analogy:** Parang **summary ng libro** — instead na basahin mo lahat ng 500 pages, kunin mo lang yung key points.

**Techniques:**

| Technique | Pano gumagana |
|-----------|---------------|
| PCA (Principal Component Analysis) | Finds the most important "directions" in data |
| t-SNE | Para sa visualization — projects high-dimensional data to 2D/3D |
| Autoencoders | Neural network na nag-c-compress tapos nag-r-reconstruct |

**Use case:** Image compression, data visualization, speeding up training

---

## 🌐 Neural Networks / Deep Learning

**Ano to:** Inspired by human brain — layers of interconnected nodes na natututo ng complex patterns.

**Pinoy analogy:** Parang **utak ng tao** — maraming neurons na connected, each layer nag-p-process ng iba-ibang level of detail.

**Techniques:**

| Technique | Para saan |
|-----------|-----------|
| ANN (Artificial Neural Network) | Basic neural net — general purpose |
| CNN (Convolutional Neural Network) | Images — face recognition, defect detection |
| RNN (Recurrent Neural Network) | Sequential data — time series, text |
| LSTM (Long Short-Term Memory) | Improved RNN — remembers long sequences |
| Transformer | Behind GPT, Claude, BERT — best for language |
| GAN (Generative Adversarial Network) | Generates new data — fake images, deepfakes |

**Use case:** Image recognition, NLP, speech-to-text, AI art generation

---

## 🌳 Ensemble Methods (Power of Many)

**Ano to:** Nag-c-combine ng multiple models para mas accurate ang prediction.

**Pinoy analogy:** Parang **"Ask the Audience" sa Who Wants to Be a Millionaire** — mas reliable ang sagot ng marami kaysa isa lang.

**Techniques:**

| Technique | Pano gumagana |
|-----------|---------------|
| Random Forest | Maraming decision trees, majority vote |
| Gradient Boosting (XGBoost, LightGBM) | Each new model fixes errors ng previous model |
| Bagging | Train multiple models on different subsets of data |
| Stacking | Different model types combined, another model decides final answer |

**Use case:** Kaggle competitions (almost always ensemble ang winner), fraud detection, credit scoring

---

## 🔍 Anomaly Detection (Hanapin ang Kakaiba)

**Ano to:** Identifies data points na "hindi normal" — outliers.

**Pinoy analogy:** Parang **security guard na nag-m-monitor ng CCTV** — "Lahat normal... teka, bakit may tao na naka-ski mask sa loob ng bank?"

**Techniques:**

| Technique | Pano gumagana |
|-----------|---------------|
| Isolation Forest | Isolates anomalies — outliers are easier to separate |
| One-Class SVM | Learns what "normal" looks like, flags anything different |
| Autoencoders | Learns to reconstruct normal data — high error = anomaly |

**Use case:** Fraud detection, network intrusion, manufacturing defect detection

---

## 💬 Natural Language Processing (NLP)

**Ano to:** Techniques para sa text/language understanding.

**Pinoy analogy:** Parang **interpreter** — nag-t-translate ng human language to something computers understand.

**Techniques:**

| Technique | Para saan |
|-----------|-----------|
| Tokenization | Break text into words/subwords |
| Word Embeddings (Word2Vec) | Convert words to numbers na may meaning |
| Sentiment Analysis | Positive, negative, o neutral ang text? |
| Named Entity Recognition (NER) | Find names, places, dates in text |
| Text Summarization | Shorten long documents |
| Machine Translation | Translate between languages |

**Use case:** Chatbots, document summarization, search engines

---

## 👁️ Computer Vision

**Ano to:** Techniques para sa image/video understanding.

**Pinoy analogy:** Parang **mata ng robot** — natututo mag-recognize ng objects, faces, at scenes.

**Techniques:**

| Technique | Para saan |
|-----------|-----------|
| Image Classification | "Ano ito?" — cat, dog, car |
| Object Detection | "Nasaan ang mga objects?" — bounding boxes |
| Semantic Segmentation | Pixel-level classification — every pixel has a label |
| Face Recognition | Identify specific people |
| OCR (Optical Character Recognition) | Extract text from images |

**Use case:** Self-driving cars, medical imaging, quality inspection sa factory

---

## 🎯 Summary: Kailan Gamitin Ano?

| Problem | Technique |
|---------|-----------|
| Predict a number | Regression |
| Predict a category | Classification |
| Group similar items | Clustering |
| Find weird/unusual data | Anomaly Detection |
| Understand text | NLP |
| Understand images | Computer Vision / CNN |
| Complex patterns | Deep Learning |
| Maximum accuracy | Ensemble Methods |
| Too many columns | Dimensionality Reduction |

---

**Key takeaway:** Ang ML techniques ay **tools sa toolbox** — walang "best" technique for everything. Depende sa problem mo kung alin ang gagamitin. Minsan kailangan mo mag-experiment ng iba-iba bago mo makita kung alin ang best fit.
