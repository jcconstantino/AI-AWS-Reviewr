# Types of Bias in AI/ML — AWS AI Practitioner Exam (Pinoy Version) 🇵🇭

Lahat ng bias types na kailangan mong malaman para sa exam.

---

## 🎯 Ano ang Bias sa AI?

**Ano to:** Systematic errors na nagre-result sa **unfair o inaccurate** outcomes. Yung AI nag-f-favor ng isang group over another, o may consistent na mali sa predictions.

**Pinoy analogy:** Parang **biased na referee sa basketball** — hindi sinasadya (minsan), pero laging pabor sa isang team. Yung AI, ganun din — pag biased ang training data o process, biased din ang output.

---

## 📋 Types of Bias

---

### 1. Selection Bias (Sampling Bias)

**Ano to:** Yung training data **hindi representative** ng real-world population. May groups na over-represented o under-represented.

**Pinoy analogy:** Parang **survey na sa Makati lang ginawa** tapos sinabi mong "ito ang opinion ng buong Pilipinas." Hindi representative — wala kang respondents from provinces.

**Example:**
- Facial recognition trained mostly on light-skinned faces → poor accuracy on darker skin tones
- Hiring model trained only on data from one city → biased against applicants from other regions

**Pano i-fix:** Ensure diverse, representative training data from all relevant groups.

---

### 2. Measurement Bias

**Ano to:** Yung **data collection method** mismo may systematic error. Yung way na kino-collect ang data ay flawed.

**Pinoy analogy:** Parang **weighing scale na laging +2 kilos** — lahat ng measurements mo mali, hindi dahil sa tao, kundi dahil sa tool.

**Example:**
- Using arrest records as proxy for "criminal behavior" — pero arrests are biased by policing patterns
- Health data collected only from hospital visits — misses healthy people who don't go to hospitals

**Pano i-fix:** Validate measurement tools. Use multiple data sources. Question if proxy variables truly represent what you're measuring.

---

### 3. Confirmation Bias

**Ano to:** Yung model (o developer) **reinforces existing beliefs/stereotypes** — hinahanap lang yung evidence na sumusuporta sa existing assumption.

**Pinoy analogy:** Parang **tao na naniniwala na "lahat ng taga-X ay ganito"** — puro yung examples na nagco-confirm lang ang pinapansin, yung mga counter-examples ignored.

**Example:**
- Developer only tests model on cases that confirm it works → misses failure cases
- Model trained on historical hiring data that already discriminated → perpetuates the discrimination

**Pano i-fix:** Actively look for counter-examples. Test on diverse edge cases. Have diverse team review results.

---

### 4. Reporting Bias

**Ano to:** Yung data **hindi nag-r-reflect ng true frequency** kasi certain outcomes are more likely to be reported/recorded.

**Pinoy analogy:** Parang **news** — puro bad news ang nire-report, pero hindi ibig sabihin na puro masama ang nangyayari sa mundo. Over-represented lang yung negative events.

**Example:**
- Product reviews skew negative (unhappy people more likely to write reviews)
- Medical data over-reports rare diseases (common conditions often go unrecorded)
- Social media data over-represents extreme opinions

**Pano i-fix:** Acknowledge reporting gaps. Supplement with actively collected data. Weight data appropriately.

---

### 5. Automation Bias

**Ano to:** Humans **over-trust** the AI output — hindi na nag-c-critical think kasi "sabi ng computer eh."

**Pinoy analogy:** Parang **blindly following Waze** kahit obvious na mali yung directions — "Sabi ni Waze eh!" kahit papunta ka na sa ilog.

**Example:**
- Doctor accepts AI diagnosis without double-checking
- HR approves all AI-recommended candidates without review
- Pilot ignores own judgment because autopilot says otherwise

**Pano i-fix:** Human-in-the-loop. Training users to critically evaluate AI outputs. Never remove human oversight for critical decisions.

---

### 6. Societal Bias (Historical Bias)

**Ano to:** Yung training data reflects **existing societal inequalities** — kahit accurate ang data, biased pa rin kasi biased ang society.

**Pinoy analogy:** Parang **nag-aral ka ng history books na puro perspective ng colonizers** — accurate yung data na yun sa time na yun, pero biased pa rin ang perspective.

**Example:**
- "Doctor" associated with male, "nurse" with female in training data — reflects historical gender roles
- Loan approval data from decades of discriminatory lending → model learns to discriminate too
- Word embeddings: "programmer" closer to "man" than "woman"

**Pano i-fix:** Acknowledge historical context. Apply fairness constraints. Re-balance training data. Use SageMaker Clarify to detect.

---

### 7. Exclusion Bias (Omission Bias)

**Ano to:** Important features o groups **na-exclude** during data collection o preprocessing.

**Pinoy analogy:** Parang **gumawa ka ng class picture pero hindi mo sinali yung mga absent** — incomplete ang representation.

**Example:**
- Removing "gender" column thinking it removes bias — pero other correlated features (height, name) still encode gender
- Not collecting data from rural areas → model doesn't work for rural users
- Dropping rows with missing values → systematically removes certain demographics

**Pano i-fix:** Audit what's missing. Understand why data is missing. Consider if exclusion disproportionately affects certain groups.

---

### 8. Recall Bias

**Ano to:** Yung data depends on **people's memory** — at memory is unreliable and selective.

**Pinoy analogy:** Parang **nag-survey ka kung ilang beses kumain ng junk food this week** — yung mga health-conscious mag-u-underreport, yung iba mag-o-overreport.

**Example:**
- Patient self-reported symptoms (may forget or exaggerate)
- Survey asking "how many hours did you exercise last month?"
- Eyewitness testimony data

**Pano i-fix:** Use objective measurements when possible. Cross-validate with other data sources.

---

### 9. Observer Bias (Experimenter Bias)

**Ano to:** Yung tao na nag-l-label ng data **influenced by their own expectations** — unconsciously labeling in a biased way.

**Pinoy analogy:** Parang **teacher na may favorite student** — unconsciously nagbibigay ng higher grades sa favorite kahit same quality ng work.

**Example:**
- Data labelers rating sentiment differently based on perceived gender of author
- Radiologist more likely to "find" tumors when told patient is high-risk
- Annotators labeling ambiguous text based on their own cultural perspective

**Pano i-fix:** Multiple labelers per data point. Clear labeling guidelines. Inter-annotator agreement metrics. Blind labeling (remove identifying info).

---

### 10. Survivorship Bias

**Ano to:** Yung data contains only **"survivors" or successes** — yung failures/dropouts hindi kasama.

**Pinoy analogy:** Parang **nag-interview ka lang ng successful entrepreneurs** tapos conclude mo na "lahat ng nag-start ng business, naging successful." Hindi mo nakita yung 90% na nag-fail.

**Example:**
- Training on data from current employees only → doesn't capture why others left/were rejected
- Analyzing only companies that survived → ignoring patterns that led to failure
- Student performance data only from those who graduated

**Pano i-fix:** Actively seek data from failures/dropouts. Acknowledge what's missing from your dataset.

---

### 11. Funding Bias (Sponsorship Bias)

**Ano to:** Research o model development **influenced by who's paying** — results skewed toward funder's interests.

**Pinoy analogy:** Parang **research funded by a cigarette company** na conclude na "hindi naman ganun ka-harmful ang smoking." Sino nagbayad, siya nasusunod.

**Example:**
- AI model for drug effectiveness funded by pharmaceutical company
- Benchmark results cherry-picked to favor sponsor's product

**Pano i-fix:** Transparency in funding sources. Independent validation. Peer review.

---

### 12. Algorithmic Bias (Model Bias)

**Ano to:** Yung **algorithm itself** introduces bias through its design, architecture, o optimization objective.

**Pinoy analogy:** Parang **rules ng game na pabor sa isang team** — kahit fair yung players, yung rules mismo ang biased.

**Example:**
- Optimizing for "click-through rate" → promotes sensational/divisive content
- Model architecture that works better for majority language (English) than minority languages
- Loss function that penalizes errors equally → ignores that some errors are more harmful

**Pano i-fix:** Audit model decisions across groups. Use fairness-aware algorithms. Test for disparate impact.

---

## 🔬 AWS SageMaker Clarify — Bias Metrics

### Pre-Training Bias Metrics (Before Training)

Detects bias **sa data** bago pa mag-train:

| Metric | Ano chine-check |
|--------|-----------------|
| Class Imbalance (CI) | May group ba na mas marami sa data? |
| Difference in Proportions of Labels (DPL) | Iba-iba ba ang positive outcome rate per group? |
| KL Divergence | Gaano ka-different ang distributions between groups? |
| Jensen-Shannon Divergence | Similar to KL pero symmetric |
| Lp-norm | Overall difference in distributions |
| Total Variation Distance | Maximum difference between distributions |
| Kolmogorov-Smirnov (KS) | Statistical test for distribution differences |
| Conditional Demographic Disparity (CDD) | Disparity after controlling for legitimate factors |

### Post-Training Bias Metrics (After Training)

Detects bias **sa model predictions**:

| Metric | Ano chine-check |
|--------|-----------------|
| Difference in Positive Proportions in Predicted Labels (DPPL) | Iba-iba ba ang prediction rates per group? |
| Disparate Impact (DI) | Ratio of positive predictions between groups |
| Accuracy Difference (AD) | Iba-iba ba ang accuracy per group? |
| Treatment Equality (TE) | Ratio of false positives to false negatives per group |
| Recall Difference (RD) | Iba-iba ba ang recall per group? |
| Conditional Demographic Disparity in Predicted Labels (CDDPL) | Disparity in predictions after controlling for factors |
| Counterfactual Fliptest | Pag pinalitan mo lang ang protected attribute, nagbago ba ang prediction? |

---

## 🎯 Summary Table

| Bias Type | Saan nanggagaling | Pinoy Analogy |
|-----------|-------------------|---------------|
| Selection | Data not representative | Survey sa Makati lang = "buong Pilipinas" |
| Measurement | Flawed data collection tool | Weighing scale na +2 kilos |
| Confirmation | Reinforcing existing beliefs | Pinapansin lang yung nagco-confirm |
| Reporting | Over/under-reporting of events | News = puro bad news |
| Automation | Over-trusting AI | "Sabi ni Waze eh!" |
| Societal/Historical | Society itself is biased | History books ng colonizers |
| Exclusion | Important data left out | Class picture na walang absent |
| Recall | Unreliable human memory | "Ilang beses ka nag-gym?" |
| Observer | Labeler's own bias | Teacher na may favorite |
| Survivorship | Only successes in data | Interview successful people lang |
| Funding | Funder influences results | Cigarette company research |
| Algorithmic | Model design itself | Rules ng game na biased |

---

## 📝 Exam-Style Questions

| Kung ang tanong ay about... | Sagot |
|-----------------------------|-------|
| Training data not representing all groups | Selection Bias |
| Data collection method is flawed | Measurement Bias |
| Model perpetuates historical discrimination | Societal/Historical Bias |
| Humans blindly trusting AI output | Automation Bias |
| Only successful cases in training data | Survivorship Bias |
| Detecting bias in data before training | SageMaker Clarify (Pre-training metrics) |
| Detecting bias in model predictions | SageMaker Clarify (Post-training metrics) |
| Explaining why model made a decision | SageMaker Clarify (SHAP/Explainability) |
| Important features removed from data | Exclusion Bias |
| Labelers influenced by their own views | Observer Bias |

---

**Bottom line para sa exam:** Bias can enter at **any stage** — data collection, labeling, training, deployment. AWS tool for detecting bias = **SageMaker Clarify** (both pre-training at post-training metrics). Always remember: **biased data = biased model**. 🎯
