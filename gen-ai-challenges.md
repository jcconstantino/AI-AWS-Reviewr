# Generative AI Challenges & Drawbacks — AWS AI Practitioner Exam (Pinoy Version) 🇵🇭

Mga common problems at limitations ng Generative AI na lalabas sa exam.

---

## ⚠️ Major Challenges

---

### 1. Hallucination

**Ano to:** AI generates **confident pero WRONG** information. Nag-i-imbento ng facts, citations, o data na hindi totoo.

**Pinoy analogy:** Parang **estudyante na nag-b-BS sa oral exam** — mukhang confident, maganda ang delivery, pero gawa-gawa lang yung content.

**Examples:**
- Cites research papers na hindi naman existing
- Invents historical events na hindi nangyari
- Gives wrong code that looks correct syntactically

**Mitigation:**

| Strategy | Pano |
|----------|------|
| RAG (Retrieval Augmented Generation) | Ground responses in actual documents |
| Low temperature (0-0.2) | Less creative = less hallucination |
| Specific prompts | "Only answer based on provided context. Say 'I don't know' if unsure" |
| Human review | Always verify critical outputs |
| Guardrails | Block responses when confidence is low |
| Citations | Ask model to cite sources (then verify them) |

**Exam tip:** Reducing hallucination → **RAG / Knowledge Bases**

---

### 2. Bias and Fairness

**Ano to:** Model reflects and amplifies **biases from training data** — discriminates against certain groups.

**Pinoy analogy:** Parang **anak na natuto ng bad habits from parents** — hindi sinasadya, pero na-absorb niya yung biases ng environment niya.

**Examples:**
- Resume screening that favors one gender
- Loan approval that discriminates by race
- Image generation that stereotypes certain cultures

**Mitigation:**

| Strategy | AWS Tool |
|----------|----------|
| Detect bias in data | SageMaker Clarify (pre-training metrics) |
| Detect bias in predictions | SageMaker Clarify (post-training metrics) |
| Diverse training data | Data collection best practices |
| Fairness constraints | Algorithmic fairness techniques |
| Regular audits | Ongoing monitoring |

---

### 3. Toxicity and Harmful Content

**Ano to:** Model generates **offensive, violent, sexual, o dangerous** content.

**Pinoy analogy:** Parang **bata na natutunan ang bad words sa internet** — na-expose sa lahat ng content, kaya minsan lumalabas yung inappropriate.

**Examples:**
- Hate speech or discriminatory language
- Instructions for dangerous activities
- Sexually explicit content
- Violent or threatening responses

**Mitigation:**

| Strategy | AWS Tool |
|----------|----------|
| Content filtering | Bedrock Guardrails (hate, violence, sexual, insults categories) |
| Topic blocking | Bedrock Guardrails (denied topics) |
| Word filters | Bedrock Guardrails (word/phrase filters) |
| Output moderation | Post-processing filters |

---

### 4. Data Privacy and Security

**Ano to:** Risk na **sensitive/personal data** ma-leak through model outputs — either from training data or user inputs.

**Pinoy analogy:** Parang **chismosa na narinig ang secret mo** — baka ma-share niya sa iba without permission.

**Risks:**
- Model memorizes and regurgitates PII from training data
- User inputs stored and potentially exposed
- Proprietary business data leaked through prompts
- Model inversion attacks (extracting training data)

**Mitigation:**

| Strategy | AWS Tool |
|----------|----------|
| PII redaction in responses | Bedrock Guardrails |
| Sensitive data discovery | Amazon Macie |
| Encryption | AWS KMS (at rest + in transit) |
| Access control | IAM policies, VPC isolation |
| Data residency | Choose specific AWS regions |

---

### 5. High Cost

**Ano to:** GenAI models are **expensive** — training costs millions, inference costs add up fast at scale.

**Pinoy analogy:** Parang **luxury car** — maganda at mabilis, pero ang mahal ng gas, maintenance, at insurance.

**Cost breakdown:**

| Cost Type | Details |
|-----------|---------|
| Training | Millions of dollars for foundation models |
| Fine-tuning | Thousands per run (GPU hours) |
| Inference (per token) | Adds up with high volume |
| Infrastructure | GPU instances are expensive |
| Data storage | Large datasets and model artifacts |

**Mitigation:**

| Strategy | Pano |
|----------|------|
| Use smaller models for simple tasks | Nova Lite instead of Claude Opus |
| Prompt optimization | Shorter prompts = fewer tokens = less cost |
| Caching | Cache common responses |
| Batch processing | Cheaper than real-time for bulk tasks |
| Right-size model selection | Don't use Opus for tasks Haiku can handle |

---

### 6. Lack of Explainability (Black Box)

**Ano to:** Hindi mo ma-explain **bakit** ganun ang output ng model. Billions of parameters = impossible to trace exact reasoning.

**Pinoy analogy:** Parang **tinanong mo yung bata "bakit yan ang sagot mo?" tapos sabi niya "basta."** Hindi niya ma-explain yung reasoning.

**Problems:**
- Can't debug wrong answers easily
- Hard to satisfy regulatory requirements (explainability mandates)
- Users don't trust what they can't understand
- Difficult to improve specific failure modes

**Mitigation:**

| Strategy | Pano |
|----------|------|
| Chain-of-thought prompting | Force model to show reasoning |
| RAG with citations | Show source documents |
| Model cards | Document capabilities and limitations |
| Simpler models for critical decisions | Use interpretable ML where explainability is required |

---

### 7. Intellectual Property (IP) and Copyright Issues

**Ano to:** Generated content may **infringe on copyrighted material** — kasi trained on internet data na may copyrighted content.

**Pinoy analogy:** Parang **artist na "inspired" ng iba** — fine line between inspiration at plagiarism. Minsan yung output halos copy na ng existing work.

**Risks:**
- Generated text too similar to copyrighted source
- Generated images resembling copyrighted artwork
- Code generation that copies licensed code
- Legal liability unclear — who owns AI-generated content?

**Mitigation:**

| Strategy | Pano |
|----------|------|
| Indemnification | Some providers (Amazon) offer IP indemnity for certain models |
| Watermarking | Titan models add invisible watermarks to generated images |
| Human review | Check outputs for similarity to known works |
| Usage policies | Clear terms on how generated content can be used |

---

### 8. Latency and Performance

**Ano to:** GenAI models are **slow** compared to traditional software — generating text token by token takes time.

**Pinoy analogy:** Parang **handwritten letter vs text message** — mas maganda ang output, pero mas matagal.

**Issues:**
- Large models = slower inference
- Long outputs = more time (token by token)
- Cold starts for serverless deployments
- Not suitable for real-time, low-latency requirements

**Mitigation:**

| Strategy | Pano |
|----------|------|
| Smaller/faster models | Haiku, Nova Lite for speed |
| Streaming responses | Show output as it generates |
| Provisioned throughput | Pre-allocate capacity in Bedrock |
| Caching | Store frequent responses |
| Async processing | Queue requests for non-urgent tasks |

---

### 9. Non-Deterministic Outputs

**Ano to:** Same prompt, **different answer every time**. Hindi consistent ang output.

**Pinoy analogy:** Parang **tinanong mo yung kaibigan mo ng same question 3 times** — iba-iba ang sagot every time. Confusing.

**Problems:**
- Hard to test and validate
- Inconsistent user experience
- Difficult to reproduce bugs
- Compliance issues (need consistent decisions)

**Mitigation:**

| Strategy | Pano |
|----------|------|
| Temperature = 0 | Most deterministic output |
| Seed parameter | Some models support fixed seed for reproducibility |
| Structured output | Force JSON/template format |
| Validation layer | Post-processing to ensure consistency |

---

### 10. Limited Context Window

**Ano to:** Models can only process a **limited amount of text** at once. Pag sobra, nawawala ang earlier context.

**Pinoy analogy:** Parang **tao na may short-term memory** — kaya lang mag-remember ng last few minutes ng conversation. Pag mahaba na, nakakalimutan na yung simula.

**Context window sizes:**

| Model | Context Window |
|-------|---------------|
| Claude Sonnet | 200K tokens (~150K words) |
| Nova Pro | 300K tokens |
| Llama 3 | 128K tokens |
| GPT-4 | 128K tokens |

**Problems:**
- Can't process very long documents in one go
- Loses context in long conversations
- "Lost in the middle" — forgets info in the middle of long context

**Mitigation:**

| Strategy | Pano |
|----------|------|
| RAG | Retrieve only relevant chunks instead of full documents |
| Summarization | Summarize earlier context |
| Chunking | Break long documents into pieces |
| Sliding window | Process in overlapping segments |

---

### 11. Environmental Impact

**Ano to:** Training and running large AI models consumes **massive energy** — significant carbon footprint.

**Pinoy analogy:** Parang **SUV vs bicycle** — mas powerful, pero mas malaki ang carbon footprint.

**Facts:**
- Training GPT-3 estimated at ~1,287 MWh of electricity
- Single query uses ~10x more energy than a Google search
- Data centers require significant cooling

**Mitigation:** Use efficient models, batch processing, carbon-aware scheduling, smaller models when possible.

---

### 12. Over-Reliance and Deskilling

**Ano to:** Users become **too dependent** on AI — lose their own skills and critical thinking.

**Pinoy analogy:** Parang **calculator dependency** — pag nawala ang calculator, hindi na kaya mag-mental math. Ganun din sa AI — pag laging AI ang gumagawa, nawawala yung sarili mong skills.

**Risks:**
- Developers stop learning to code properly
- Writers lose writing skills
- Critical thinking decreases
- Can't function when AI is unavailable

**Mitigation:** Use AI as assistant, not replacement. Maintain human skills. Always review and understand AI outputs.

---

## 🎯 Summary Table

| Challenge | Risk Level | Primary Mitigation |
|-----------|-----------|-------------------|
| Hallucination | 🔴 High | RAG, low temperature, human review |
| Bias/Fairness | 🔴 High | SageMaker Clarify, diverse data |
| Toxicity | 🔴 High | Bedrock Guardrails |
| Data Privacy | 🔴 High | Guardrails PII redaction, KMS, Macie |
| High Cost | 🟡 Medium | Right-size model, caching, optimization |
| Black Box | 🟡 Medium | CoT prompting, RAG with citations |
| IP/Copyright | 🟡 Medium | Indemnification, watermarking, review |
| Latency | 🟡 Medium | Smaller models, streaming, caching |
| Non-Deterministic | 🟡 Medium | Temperature=0, structured output |
| Context Window | 🟡 Medium | RAG, chunking, summarization |
| Environmental | 🟢 Low | Efficient models, batch processing |
| Over-Reliance | 🟢 Low | Human-in-the-loop, training |

---

## 📝 Exam-Style Questions

| Kung ang tanong ay about... | Sagot |
|-----------------------------|-------|
| AI generating false information confidently | Hallucination |
| Mitigating hallucination | RAG / Knowledge Bases |
| Filtering harmful AI output | Bedrock Guardrails |
| Protecting personal data in AI responses | Bedrock Guardrails (PII redaction) |
| AI model giving different answers each time | Non-deterministic outputs (fix: temperature=0) |
| AI perpetuating discrimination | Bias (fix: SageMaker Clarify) |
| Can't explain why AI made a decision | Lack of explainability |
| AI output too similar to copyrighted work | IP/Copyright issues |
| Model can't handle very long documents | Context window limitation (fix: RAG) |
| Humans trusting AI without verification | Automation bias / Over-reliance |

---

**Bottom line para sa exam:** Top 3 challenges na madalas i-tanong = **Hallucination** (fix: RAG), **Bias** (fix: Clarify), **Toxicity** (fix: Guardrails). Alam mo yang tatlo = majority ng questions covered. 🎯
