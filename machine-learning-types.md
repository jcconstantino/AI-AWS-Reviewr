# Machine Learning Types — Learning Process (Pinoy Version) 🇵🇭

---

## 1. Supervised Learning (May Guro)

**Pano natututo:** May **teacher** na nagbibigay ng tamang sagot habang nag-aaral.

**Pinoy analogy:** Parang **reviewer para sa board exam** — may tanong, may sagot. Paulit-ulit mong sinasagutan hanggang ma-master mo yung pattern.

**Process:**

1. Bigyan mo ng maraming examples na may label (input + tamang sagot)
2. Yung model, hahanap ng pattern between input at output
3. Pag may bagong input, kaya na niyang hulaan yung sagot

**Halimbawa:**

- Input: 1,000 photos ng tela na may label ("defective" o "good")
- Model learns: "Pag ganito yung pattern ng thread, defective yan"
- Bagong photo → model predicts: "defective" ✅

**Use cases:**

- Spam detection (spam o hindi?)
- Image classification (aso o pusa?)
- Price prediction (magkano ang bahay based sa location, size?)

---

## 2. Unsupervised Learning (Walang Guro — Sariling Diskubre)

**Pano natututo:** **Walang teacher**, walang tamang sagot. Yung model mismo ang naghahanap ng hidden patterns sa data.

**Pinoy analogy:** Parang **bata na nag-so-sort ng Lego by color** — walang nagsabi na "pula dito, asul doon." Siya mismo nag-figure out na magkakamukha yung iba.

**Process:**

1. Bigyan mo ng maraming data **walang labels**
2. Yung model, maghahanap ng natural groupings o patterns
3. Ikaw ang mag-i-interpret kung ano yung meaning ng groups

**Halimbawa:**

- Input: Purchase history ng 10,000 customers (walang label)
- Model discovers: "May 3 groups — madalas bumili ng weekend, madalas bumili ng gabi, madalas bumili ng sale"
- Ikaw ang mag-name: "Weekend shoppers, Night owls, Bargain hunters"

**Use cases:**

- Customer segmentation (i-group ang customers by behavior)
- Anomaly detection (unusual na transaction = possible fraud)
- Recommendation engines ("customers who bought X also bought Y")

---

## 3. Reinforcement Learning (Trial and Error — May Reward System)

**Pano natututo:** Walang teacher na nagbibigay ng sagot. Instead, may **reward at punishment** system. Yung model (agent) nag-e-explore, nag-t-try ng actions, tapos natututo based sa results.

**Pinoy analogy:** Parang **tuta na tinuturuan ng tricks** 🐕

- Umupo → treat (reward!) → "Ah, pag umupo ako, may pagkain!"
- Kumagat ng sapatos → "Ay!" (punishment) → "Hindi pala maganda yun"
- Paulit-ulit hanggang ma-master

**O kaya:** Parang **bata na naglalaro ng video game** — walang manual, trial and error lang. Pag namatay, alam mo nang huwag gawin yun. Pag naka-score, uulitin mo.

**Process:**

1. May **Agent** (yung learner) na nasa **Environment** (yung mundo)
2. Agent takes an **Action** (gumagalaw, pumipili)
3. Environment gives back a **State** (ano nangyari) + **Reward** (maganda o masama ba yung ginawa?)
4. Agent adjusts strategy → tries again
5. Paulit-ulit hanggang ma-maximize yung total reward

**Mga Key Concepts:**

| Concept | Pinoy Explanation |
|---------|-------------------|
| Agent | Yung nag-aaral — parang player sa game |
| Environment | Yung mundo/game na kinakalaban niya |
| State | Current situation — "nasaan ako ngayon?" |
| Action | Yung ginagawa ng agent — "kaliwa ba o kanan?" |
| Reward | Points — positive kung maganda, negative kung masama |
| Policy | Strategy ng agent — "pag ganito ang situation, gawin ko ito" |
| Exploration | Nag-t-try ng bagong bagay — "what if dito ako pumunta?" |
| Exploitation | Ginagamit yung alam na niyang effective — "ito na yung best move" |

**Halimbawa (Real-world):**

- **Self-driving car:** Agent = kotse. Action = liko, preno, gas. Reward = safe arrival. Punishment = aksidente.
- **Game AI:** AlphaGo learned Go by playing millions of games against itself
- **AWS DeepRacer:** Toy car na natututo mag-drive sa track through trial and error
- **Robot sa factory:** Natututo mag-pick ng items — reward pag tama ang grip, punishment pag nahulog

---

## 4. Semi-Supervised Learning (Konting Guro, Maraming Sariling Aral)

**Pano natututo:** Mix — **konti lang ang may label**, marami ang walang label. Yung model, natututo sa konting labeled data tapos nag-a-apply sa malaking unlabeled data.

**Pinoy analogy:** Parang **OJT** — konti lang yung formal training, pero marami kang natututo sa actual work by observing patterns.

**Process:**

1. May 100 labeled examples + 10,000 unlabeled examples
2. Model learns basic patterns from labeled data
3. Applies that knowledge to make sense of unlabeled data
4. Gets better over time

**Bakit useful:** Kasi sa real world, **mahal at matagal ang mag-label ng data**. Imagine mag-label ka ng 1 million images manually — ang tagal! Semi-supervised lets you use mostly unlabeled data.

---

## 5. Self-Supervised Learning (Sarili Niya Gumawa ng Labels)

**Pano natututo:** Yung model **gumagawa ng sarili niyang training task** from unlabeled data.

**Pinoy analogy:** Parang **bata na nag-aaral mag-basa** by covering words and guessing — "The cat sat on the \_\_\_." Sarili niya ang nag-quiz sa sarili niya.

**Halimbawa:**

- GPT/LLMs: Trained by predicting the next word — "Ang ganda ng \_\_\_" → "araw"
- BERT: Trained by filling in blanked-out words in sentences
- Image models: Trained by predicting missing patches of an image

**Bakit powerful:** Ito yung behind ChatGPT, Claude, at lahat ng foundation models. Kaya sila super magaling kasi natuto sa **buong internet** without needing humans to label everything.

---

## 🎯 Summary Table

| Type | May Guro? | Pano Natututo | Pinoy Analogy |
|------|-----------|---------------|---------------|
| Supervised | ✅ Oo, may tamang sagot | Input + correct answer, paulit-ulit | Board exam reviewer |
| Unsupervised | ❌ Wala | Sariling diskubre ng patterns | Bata nag-so-sort ng Lego |
| Reinforcement | ❌ Wala, pero may reward | Trial and error + reward/punishment | Tuta na tinuturuan ng tricks |
| Semi-Supervised | 🔀 Konti lang | Mix ng labeled + unlabeled | OJT — konting training, maraming self-learning |
| Self-Supervised | ❌ Sarili niya | Gumagawa ng sariling quiz | Bata nag-aaral mag-basa by guessing |

---

**Key takeaway:** Reinforcement Learning ang pinaka-unique kasi **walang "tamang sagot" na binibigay** — natututo siya through experience, parang tao na natututo sa buhay through trial and error. Kaya siya ang ginagamit sa robotics, games, at autonomous systems.
