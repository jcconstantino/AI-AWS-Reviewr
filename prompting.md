# Types of Prompting — AWS AI Practitioner Exam (Pinoy Version) 🇵🇭

Lahat ng prompting techniques na kailangan mong malaman para sa exam.

---

## 🎯 Ano ang Prompt Engineering?

**Ano to:** Yung art of crafting instructions para makuha ang **best possible output** from an AI model.

**Pinoy analogy:** Parang **pag-o-order sa restaurant** — mas specific ka ("medium rare, no onions, extra sauce"), mas maganda yung makukuha mo. Kung "bahala ka" lang, baka hindi mo gusto yung lalabas.

---

## 📋 Types of Prompting Techniques

---

### 1. Zero-Shot Prompting

**Ano to:** Direct instruction — **walang example**. Basta sabihin mo lang kung ano ang gusto mo.

**Pinoy analogy:** Parang sinabi mo sa bata: "Mag-drawing ka ng pusa" — walang pinakitang sample, kaya niya naman.

**Example:**

```
Prompt: "Classify the following text as positive, negative, or neutral: 
'The food was amazing and the service was great!'"

Output: "Positive"
```

**Kailan gamitin:** Simple tasks na obvious naman kung ano ang expected output.

---

### 2. One-Shot Prompting

**Ano to:** Nagbigay ka ng **isang example** bago ang actual task.

**Pinoy analogy:** Parang sinabi mo: "Ganito ang gusto ko ha — *ito yung sample* — ngayon ikaw naman."

**Example:**

```
Prompt: "Classify the sentiment:

Example: 'I love this product!' → Positive

Now classify: 'The delivery was terrible and the item was broken.'"

Output: "Negative"
```

**Kailan gamitin:** Pag gusto mong i-set yung format o style ng output.

---

### 3. Few-Shot Prompting

**Ano to:** Nagbigay ka ng **2-5 examples** bago ang actual task. Mas maraming examples = mas clear sa model kung ano ang pattern.

**Pinoy analogy:** Parang **tutor na nagbigay ng sample problems with solutions** bago ang actual quiz — "Ganito ang pattern, gets mo na ba?"

**Example:**

```
Prompt: "Translate English to Filipino:

Hello → Kamusta
Thank you → Salamat
Good morning → Magandang umaga

How are you → "

Output: "Kumusta ka"
```

**Kailan gamitin:** Pag complex ang task at kailangan ng consistent format/style.

**Exam tip:** Few-shot = **provide examples to guide the model**. Ito yung most commonly asked sa exam.

---

### 4. Chain-of-Thought (CoT) Prompting

**Ano to:** Pinapag-**explain step by step** ang reasoning bago mag-final answer. Forces the model to "think out loud."

**Pinoy analogy:** Parang **math teacher na nagsabi "ipakita mo yung solution, hindi lang yung answer."** Pag step by step, mas accurate ang final answer.

**Example:**

```
Prompt: "A store has 50 apples. They sold 23 in the morning and 12 in the afternoon. 
How many are left? Think step by step."

Output: 
"Step 1: Started with 50 apples
Step 2: Sold 23 in morning → 50 - 23 = 27 remaining
Step 3: Sold 12 in afternoon → 27 - 12 = 15 remaining
Answer: 15 apples"
```

**Kailan gamitin:** Math, logic, reasoning, complex multi-step problems.

**Exam tip:** Pag ang tanong ay about improving reasoning accuracy → **Chain-of-Thought**

---

### 5. Zero-Shot Chain-of-Thought

**Ano to:** Chain-of-thought pero **walang examples** — just add "Think step by step" or "Let's think about this carefully."

**Pinoy analogy:** Parang sinabi mo lang: "Isipin mo muna mabuti bago sumagot" — walang sample, pero nag-improve yung quality ng sagot.

**Example:**

```
Prompt: "If John is taller than Mary, and Mary is taller than Tom, 
who is the shortest? Let's think step by step."
```

**Kailan gamitin:** Quick improvement ng reasoning without needing to provide examples.

---

### 6. Self-Consistency Prompting

**Ano to:** Generate **multiple answers** using Chain-of-Thought, then pick the **most common answer** (majority vote).

**Pinoy analogy:** Parang **"Ask the Audience" sa game show** — hindi ka nagtitiwala sa isang sagot lang. Tanungin mo ng maraming beses, yung pinaka-madalas na sagot ang piliin mo.

**Process:**

```
Run CoT 5 times → Got answers: 15, 15, 17, 15, 15
Majority vote → Final answer: 15
```

**Kailan gamitin:** Critical decisions na kailangan ng high confidence.

---

### 7. Retrieval-Augmented Generation (RAG) Prompting

**Ano to:** Bago sumagot ang model, **naghahanap muna ng relevant documents** from a knowledge base, tapos yun ang ginagamit na context.

**Pinoy analogy:** Parang **open-book exam** — hindi pure memorization. Binibigyan mo ng reference materials bago sumagot.

**Example:**

```
System: "Answer based ONLY on the following context:"
Context: [retrieved documents from knowledge base]
User: "What is the return policy?"
```

**Kailan gamitin:** Pag kailangan ng factual, up-to-date answers based sa specific documents. Reduces hallucination.

**Exam tip:** Reducing hallucination + grounding in company data → **RAG**

---

### 8. System Prompting (Role-Based)

**Ano to:** I-set mo yung **role, personality, at rules** ng model bago ang conversation.

**Pinoy analogy:** Parang **job description** — sinabi mo na agad kung ano ang role niya. "Ikaw ay customer service agent ng Jollibee. Laging friendly. Sagot lang about menu."

**Example:**

```
System: "You are a helpful Filipino teacher. Always respond in Taglish. 
Keep answers simple and use local examples."

User: "What is cloud computing?"
```

**Kailan gamitin:** Consistent behavior across entire conversation. Setting boundaries.

---

### 9. Template/Structured Prompting

**Ano to:** Nagbibigay ka ng **exact format/template** na gusto mong sundin ng output.

**Pinoy analogy:** Parang **fill-in-the-blanks na form** — alam na ng model kung anong structure ang expected.

**Example:**

```
Prompt: "Analyze this product review and respond in this exact format:

Sentiment: [positive/negative/neutral]
Key Points: [bullet list]
Recommended Action: [one sentence]

Review: 'The laptop is fast but the battery life is terrible...'"
```

**Kailan gamitin:** Pag kailangan ng consistent, parseable output (JSON, tables, specific format).

---

### 10. Instruction Prompting

**Ano to:** Clear, direct instructions — telling the model **exactly what to do and what NOT to do**.

**Pinoy analogy:** Parang **boss na nagbibigay ng clear instructions** — "Gawin mo ito. Huwag mong gawin ito. Ganito ang format. Deadline bukas."

**Example:**

```
Prompt: "Summarize the following article in exactly 3 bullet points. 
Use simple language. Do NOT include technical jargon. 
Each bullet should be one sentence maximum."
```

**Kailan gamitin:** Lahat ng tasks — always be specific with instructions.

---

### 11. Contextual Prompting

**Ano to:** Providing **background information/context** before the actual question para mas accurate ang sagot.

**Pinoy analogy:** Parang **nagkukwento ka muna ng background** bago mag-tanong — "So ganito yung situation namin... ano ang advice mo?"

**Example:**

```
Prompt: "Context: We are a textile manufacturing company in the Philippines 
with 200 employees. We currently use manual quality inspection.

Question: What AWS AI services would you recommend for automating 
defect detection?"
```

**Kailan gamitin:** Domain-specific questions na kailangan ng relevant context.

---

### 12. Negative Prompting (for Image Models)

**Ano to:** Telling the model what **NOT to include** in the generated image.

**Pinoy analogy:** Parang **nag-o-order ka ng pizza** — "Pepperoni please, pero **walang onions, walang anchovies**."

**Example (Stable Diffusion):**

```
Prompt: "Beautiful sunset over Manila Bay, photorealistic"
Negative prompt: "blurry, low quality, cartoon, watermark, text"
```

**Kailan gamitin:** Image generation — to avoid unwanted elements.

---

## 🎯 Summary Table

| Technique | Ano ginagawa | Kailan gamitin |
|-----------|--------------|----------------|
| Zero-Shot | Direct instruction, walang example | Simple, obvious tasks |
| One-Shot | 1 example before task | Set format/style |
| Few-Shot | 2-5 examples before task | Complex tasks, consistent output |
| Chain-of-Thought | Step-by-step reasoning | Math, logic, complex problems |
| Zero-Shot CoT | "Think step by step" (no examples) | Quick reasoning improvement |
| Self-Consistency | Multiple CoT runs, majority vote | High-confidence decisions |
| RAG | Retrieve docs first, then answer | Factual, grounded answers |
| System Prompt | Set role and rules | Consistent behavior |
| Template/Structured | Provide exact output format | Parseable, consistent format |
| Instruction | Clear do's and don'ts | All tasks — be specific |
| Contextual | Provide background info | Domain-specific questions |
| Negative Prompt | What NOT to include | Image generation |

---

## 📝 Exam-Style Questions

| Kung ang tanong ay about... | Sagot |
|-----------------------------|-------|
| No examples provided, direct task | Zero-Shot |
| Providing examples to guide output | Few-Shot |
| Improving reasoning/math accuracy | Chain-of-Thought |
| "Let's think step by step" | Zero-Shot Chain-of-Thought |
| Grounding answers in documents | RAG |
| Setting AI behavior/role for entire conversation | System Prompt |
| Reducing hallucination with external knowledge | RAG |
| Getting consistent output format | Template/Structured Prompting |
| Multiple reasoning paths, pick majority | Self-Consistency |
| Excluding elements from generated images | Negative Prompting |

---

## ⚠️ Best Practices (Exam Favorites)

1. **Be specific** — vague prompts = vague answers
2. **Provide context** — more context = better output
3. **Use examples (few-shot)** — when format matters
4. **Set constraints** — word limits, format, language
5. **Iterate** — first prompt rarely perfect, refine it
6. **Separate instructions from content** — use delimiters (""", ---, XML tags)
7. **Ask for structured output** — JSON, markdown, bullet points

---

**Bottom line para sa exam:** Zero-shot (walang example), Few-shot (may examples), Chain-of-Thought (step by step reasoning), RAG (retrieve then generate). Alam mo yang apat na yan = covered ka na sa majority ng prompting questions. 🎯
