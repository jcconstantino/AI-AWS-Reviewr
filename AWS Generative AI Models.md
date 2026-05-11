# AWS Generative AI Models — Exam Ready (Pinoy Version) 🇵🇭

Lahat ng kailangan mong malaman about **Generative AI model types** sa AWS para sa AI Practitioner exam.

---

## 🧠 Ano ang Generative AI?

**Ano to:** AI na **gumagawa ng bagong content** — text, images, code, audio, video — based sa patterns na natutunan from training data.

**Pinoy analogy:** Parang **artist na nag-aral ng 1 million paintings** — hindi niya kino-copy, pero kaya na niyang gumawa ng sarili niyang masterpiece based sa natutunan niya.

**Key difference from Traditional ML:**

| Traditional ML | Generative AI |
|----------------|---------------|
| Predicts a label or number | Creates new content |
| "Ito ba ay spam?" → Yes/No | "Gumawa ka ng email about..." → buong email |
| Classification, regression | Generation, summarization, translation |

---

## 🏗️ Foundation Models — Ano Sila?

**Ano to:** Massive pre-trained models na kaya ng maraming tasks without retraining. "Foundation" kasi sila yung base na pwede mong i-customize.

**Pinoy analogy:** Parang **college graduate** — nag-aral na ng maraming subjects. Hindi mo na kailangang turuan from scratch. I-instruct mo lang kung anong specific job ang gawin.

**Characteristics:**

- Trained on massive datasets (internet-scale)
- Billions of parameters
- Multi-task capable (one model, many uses)
- Can be fine-tuned for specific domains

---

## 📋 Types of Generative AI Models (By Architecture)

---

### 1. Large Language Models (LLMs) — Text Generation

**Ano to:** Models na trained on massive text data. Generates text, code, summaries, translations.

**Architecture:** Transformer-based (self-attention mechanism)

**Pinoy analogy:** Parang **super well-read na tao** — nabasa na niya lahat ng libro sa library, kaya kaya niyang mag-write about anything.

| Model | Provider | Strengths |
|-------|----------|-----------|
| Claude (Haiku, Sonnet, Opus) | Anthropic | Best reasoning, analysis, coding, long context (200K tokens) |
| Nova (Lite, Pro, Premier) | Amazon | Cost-effective, fast, good general purpose |
| Llama | Meta | Open-weight, customizable, versatile |
| Mistral / Mixtral | Mistral AI | Fast, efficient, mixture-of-experts architecture |
| Titan Text | Amazon | Summarization, generation, Q&A |
| Command R/R+ | Cohere | RAG-optimized, enterprise search |
| Jurassic | AI21 Labs | Multilingual, instruction-following |

**Use cases:** Chatbots, code generation, summarization, translation, Q&A

---

### 2. Diffusion Models — Image Generation

**Ano to:** Models na generates images by **starting from noise and gradually refining** it into a clear image. "Diffusion" kasi parang nag-r-reverse ng ink na nag-spread sa tubig.

**Architecture:** Learns to denoise — trained by adding noise to images, then learning to remove it step by step.

**Pinoy analogy:** Parang **sculptor** — starts with a rough block of marble (noise), tapos unti-unting tinatanggal yung excess hanggang lumabas yung masterpiece.

**Process:**

```
Pure Noise → Step 1 (less noise) → Step 2 → ... → Step N → Clear Image
```

| Model | Provider | Strengths |
|-------|----------|-----------|
| Stable Diffusion (SDXL) | Stability AI | High-quality artistic images, many styles, open-source |
| Titan Image Generator | Amazon | Text-to-image, inpainting, outpainting, background removal |
| Nova Canvas | Amazon | Image generation with built-in watermarking and safety |

**Key concepts:**

| Term | Meaning |
|------|---------|
| Text-to-image | Describe what you want → AI generates image |
| Image-to-image | Provide reference image + instructions → modified image |
| Inpainting | Edit specific part of image (fill in a region) |
| Outpainting | Extend image beyond its borders |
| Negative prompt | "Huwag mong ilagay ito sa image" |
| Steps/Iterations | More steps = more refined (pero mas matagal) |
| CFG Scale | How closely to follow the prompt (higher = more literal) |

**Use cases:** Marketing materials, product mockups, art generation, image editing

---

### 3. Large Multi-Modal Models (LMMs) — Multiple Input/Output Types

**Ano to:** Models na **kaya mag-understand AND generate** across multiple modalities — text, images, audio, video — in one model.

**Architecture:** Extended transformer na may vision encoders, audio encoders, etc. combined.

**Pinoy analogy:** Parang **pentathlete** — hindi lang runner, kaya rin mag-swim, mag-bike, mag-shoot. One person, multiple skills.

| Model | Provider | Modalities |
|-------|----------|------------|
| Claude (Sonnet/Opus) with Vision | Anthropic | Text input + Image input → Text output |
| Nova (Pro/Premier) | Amazon | Text + Image + Video input → Text output |
| Nova Reel | Amazon | Text input → Video output |
| GPT-4o (reference) | OpenAI | Text + Image + Audio → Text + Audio |
| Llama (multimodal versions) | Meta | Text + Image → Text |

**What makes it "multi-modal":**

| Capability | Example |
|------------|---------|
| Image understanding | "Ano ang nasa picture na ito?" → describes the image |
| Document analysis | Upload PDF/screenshot → extracts and explains content |
| Video understanding | Analyze video frames → summarize what happened |
| Cross-modal reasoning | "Compare this chart with this text" → analysis |

**Use cases:** Document understanding, visual Q&A, video summarization, accessibility (describe images for blind users)

---

### 4. Embedding Models — Vector Representations

**Ano to:** Converts text/images into **numerical vectors** (arrays of numbers) na nag-c-capture ng meaning. Para sa search at similarity matching.

**Architecture:** Encoder-only transformer (no generation, encoding lang)

**Pinoy analogy:** Parang **GPS coordinates** — converts address (text) into numbers na pwedeng i-compare. "Malapit ba ang Makati sa BGC?" → compare coordinates.

| Model | Provider | What it embeds |
|-------|----------|----------------|
| Titan Text Embeddings | Amazon | Text → vectors (1,536 dimensions) |
| Titan Multimodal Embeddings | Amazon | Text + Images → vectors |
| Cohere Embed | Cohere | Multilingual text → vectors |

**Bakit important:** Ito yung backbone ng **RAG (Retrieval Augmented Generation)** at **semantic search**.

**Use cases:** RAG/Knowledge Bases, semantic search, recommendation systems, duplicate detection

---

### 5. Generative Adversarial Networks (GANs)

**Ano to:** Two neural networks na nag-c-compete — **Generator** (gumagawa ng fake) vs **Discriminator** (nag-d-detect kung fake o real). Through competition, both get better.

**Architecture:** Generator + Discriminator in adversarial training loop

**Pinoy analogy:** Parang **forger vs detective** — yung forger gumagawa ng peke, yung detective humuhuli. Habang tumatagal, mas magaling na yung forger gumawa ng convincing fakes, at mas magaling na rin yung detective humuli.

**Process:**

```
Generator creates fake image
         ↓
Discriminator judges: "Real or Fake?"
         ↓
Both learn from the result → repeat
```

**Use cases:** Image generation, style transfer, data augmentation, super-resolution

> ⚠️ **Note:** GANs are older tech — mostly replaced by Diffusion Models for image generation. Pero lalabas pa rin sa exam as a concept.

---

### 6. Variational Autoencoders (VAEs)

**Ano to:** Learns a **compressed representation** (latent space) of data, then generates new data by sampling from that space.

**Architecture:** Encoder (compress) → Latent Space → Decoder (reconstruct/generate)

**Pinoy analogy:** Parang **zip file** — i-compress mo yung data into a small representation, tapos i-decompress mo into something new.

**Use cases:** Image generation, anomaly detection, drug discovery, data augmentation

---

### 7. Transformer Models (The Architecture Behind Everything)

**Ano to:** Hindi ito isang specific model — ito yung **architecture** na ginagamit ng almost all modern GenAI. Invented 2017 ("Attention Is All You Need" paper).

**Key innovation:** **Self-attention mechanism** — kaya mag-focus sa relevant parts ng input regardless of distance.

**Pinoy analogy:** Parang **speed reader** na kaya mag-focus sa important words sa buong paragraph simultaneously — hindi kailangan basahin word by word.

**Types of Transformer:**

| Type | What it does | Examples |
|------|--------------|---------|
| Encoder-only | Understanding/classification | BERT, Embeddings |
| Decoder-only | Text generation | GPT, Claude, Llama, Nova |
| Encoder-Decoder | Translation, summarization | T5, BART |

---

## 🎯 Model Types Summary Table

| Model Type | Input | Output | Example | Pinoy Analogy |
|------------|-------|--------|---------|---------------|
| LLM | Text | Text | Claude, Nova, Llama | Super well-read writer |
| Diffusion | Text (or image) | Image | Stable Diffusion, Titan Image | Sculptor from noise |
| Multi-Modal | Text + Image + Video | Text (or image/video) | Claude Vision, Nova Pro | Pentathlete — multiple skills |
| Embedding | Text/Image | Vector (numbers) | Titan Embeddings | GPS coordinates ng meaning |
| GAN | Noise/Input | Image | StyleGAN | Forger vs Detective |
| VAE | Data | New data | Various | Zip/Unzip ng data |
| Transformer | Varies | Varies | All of the above | Architecture behind everything |

---

## 📋 Models Available sa Amazon Bedrock

| Model | Provider | Type | Best For |
|-------|----------|------|----------|
| Claude (Haiku, Sonnet, Opus) | Anthropic | LLM + Multi-Modal | Reasoning, coding, analysis, vision |
| Nova Lite | Amazon | LLM | Cost-effective simple tasks |
| Nova Pro | Amazon | LLM + Multi-Modal | Balanced performance, image/video understanding |
| Nova Premier | Amazon | LLM | Complex reasoning |
| Nova Canvas | Amazon | Diffusion | Image generation |
| Nova Reel | Amazon | Multi-Modal | Video generation |
| Llama | Meta | LLM | Open-weight, customizable |
| Mistral/Mixtral | Mistral AI | LLM | Fast, efficient |
| Stable Diffusion XL | Stability AI | Diffusion | Artistic image generation |
| Titan Text | Amazon | LLM | General text tasks |
| Titan Image Generator | Amazon | Diffusion | Image generation, editing |
| Titan Embeddings | Amazon | Embedding | RAG, semantic search |
| Titan Multimodal Embeddings | Amazon | Embedding | Text + image search |
| Command R/R+ | Cohere | LLM | RAG-optimized |
| Cohere Embed | Cohere | Embedding | Multilingual search |
| Jurassic | AI21 Labs | LLM | Multilingual text |

---

## 🔑 Key Generative AI Concepts para sa Exam

### Tokens

**Ano to:** Yung unit na ginagamit ng AI para mag-process ng text. ~1 token ≈ ¾ of a word.

**Pinoy analogy:** Parang **jeepney fare** — hindi per kilometer, pero per "section." Ganun din ang AI — per token ang charge.

| Term | Meaning |
|------|---------|
| Input tokens | Yung prompt/question mo |
| Output tokens | Yung response ng AI |
| Context window | Maximum tokens na kaya i-process in one go |
| Token limit | Max output length |

---

### Inference Parameters

| Parameter | Ano ginagawa | Pinoy Analogy |
|-----------|--------------|---------------|
| Temperature | Controls creativity (0 = strict, 1 = creative) | Thermostat ng creativity |
| Top P | Controls diversity of word choices | Parang "top P percent lang ang choices" |
| Top K | Limits choices to top K words | "Top K candidates lang ang pipiliin" |
| Max Tokens | Limits response length | Word count limit sa essay |
| Stop Sequences | Tells model when to stop | "Tumigil ka pag nakita mo ito" |

---

### Prompt Engineering

**Ano to:** Yung art of crafting instructions para makuha ang best results from AI.

| Technique | Pano | Example |
|-----------|------|---------|
| Zero-shot | Walang example, direct instruction | "Translate to Filipino: Hello" |
| Few-shot | May examples bago ang actual task | "English→Filipino: Hello→Kamusta. Goodbye→___" |
| Chain-of-thought | Pinapag-explain step by step | "Think step by step before answering" |
| System prompt | Sets the role/behavior ng model | "You are a helpful Filipino teacher" |

**Exam tip:** Few-shot = provide examples. Zero-shot = no examples. Chain-of-thought = step-by-step reasoning.

---

### Fine-Tuning vs RAG vs Prompt Engineering

| Method | Kailan gamitin | Cost | Effort |
|--------|---------------|------|--------|
| Prompt Engineering | Quick adjustments, general tasks | Free | Low |
| RAG (Retrieval Augmented Generation) | Need factual answers from your documents | Medium | Medium |
| Fine-Tuning | Need model to learn new style/domain permanently | High | High |
| Continued Pre-Training | Need model to learn entirely new domain knowledge | Very High | Very High |

**Pinoy analogy:**
- **Prompt Engineering** = "Oy, ganito ang gusto ko" (instruction lang)
- **RAG** = "Eto yung reference materials, basahin mo muna bago sumagot" (open-book exam)
- **Fine-Tuning** = "Mag-aral ka ng 1 month about this topic" (specialized training)
- **Continued Pre-Training** = "Bumalik ka sa school for another degree" (full re-education)

---

### RAG (Retrieval Augmented Generation)

**Ano to:** Bago sumagot ang AI, naghahanap muna siya ng relevant info from your documents. Para less hallucination.

**Pinoy analogy:** Parang **open-book exam** — hindi pure memorization. Pwede mag-refer sa notes bago sumagot.

**Process:**

1. Documents → chunked → converted to embeddings → stored in vector database
2. User asks question → question converted to embedding
3. Vector search finds most relevant chunks
4. Relevant chunks + question sent to LLM
5. LLM generates answer grounded in actual documents

**Sa AWS:** Bedrock Knowledge Bases (uses Titan Embeddings + OpenSearch Serverless)

---

### Hallucination

**Ano to:** AI generates **confident pero WRONG** answers. Nag-i-imbento.

**Pinoy analogy:** Parang **estudyante na nag-b-BS sa oral exam** — mukhang confident, pero gawa-gawa lang yung sagot.

**Pano i-reduce:**

| Strategy | Pano |
|----------|------|
| RAG | Ground responses in real documents |
| Low temperature (0-0.2) | Less creative = less hallucination |
| Specific prompts | "Only answer based on the provided context" |
| Human review | Always verify critical outputs |
| Guardrails | Block responses when model is uncertain |

---

### Model Evaluation Metrics

| Metric | Para saan |
|--------|-----------|
| ROUGE | Measures quality of summarization (overlap with reference) |
| BLEU | Measures quality of translation |
| BERTScore | Semantic similarity between generated and reference text |
| Perplexity | How "surprised" the model is — lower = better |
| Human evaluation | Humans rate quality, relevance, safety |
| F1 Score | Balance of precision and recall |

**Exam tip:** Summarization quality → **ROUGE**. Translation quality → **BLEU**.

---

## 🏛️ AWS Generative AI Architecture Stack

```
┌─────────────────────────────────────────────┐
│           AI Applications (top)              │
│  Amazon Q, CodeWhisperer, Contact Lens      │
├─────────────────────────────────────────────┤
│         Amazon Bedrock (middle)              │
│  Foundation Models as API, RAG, Guardrails  │
├─────────────────────────────────────────────┤
│        Amazon SageMaker (bottom)             │
│  Custom training, fine-tuning, deployment   │
├─────────────────────────────────────────────┤
│          Infrastructure (base)               │
│  EC2 (GPU), Trainium, Inferentia chips      │
└─────────────────────────────────────────────┘
```

| Layer | Kung ikaw ay... |
|-------|-----------------|
| AI Applications | Gusto mo lang gamitin — walang coding | 
| Bedrock | Developer na gusto ng API access sa foundation models |
| SageMaker | Data scientist na gusto mag-train/fine-tune ng custom model |
| Infrastructure | Need full control ng hardware (rare) |

---

## 🛠️ AWS GenAI Services — Complete List

| Service | What it does | Pinoy Analogy |
|---------|--------------|---------------|
| Amazon Bedrock | Foundation models as API | Restaurant menu — pick a model, order via API |
| Amazon Q | AI assistant for business/developers | Personal assistant sa office |
| Amazon Q Developer | AI coding assistant (formerly CodeWhisperer) | Coding buddy na nag-s-suggest |
| Amazon SageMaker JumpStart | Pre-trained models ready to deploy | IKEA furniture — assemble lang |
| Amazon Comprehend | NLP — sentiment, entities, language detection | Interpreter na nag-a-analyze ng text |
| Amazon Rekognition | Image/video analysis | Security guard na may super vision |
| Amazon Textract | Extract text from documents (OCR++) | Scanner na nag-b-basa ng documents |
| Amazon Transcribe | Speech-to-text | Stenographer — nag-t-type ng sinasabi mo |
| Amazon Polly | Text-to-speech | Narrator — binabasa nang malakas ang text |
| Amazon Translate | Language translation | Google Translate pero enterprise-grade |
| Amazon Personalize | Recommendation engine | "Customers who bought X also bought Y" |
| Amazon Kendra | Intelligent enterprise search | Super librarian na nag-s-search ng documents |
| Amazon Lex | Chatbot builder | Yung AI sa customer service hotline |

---

## 📝 Exam-Style Cheat Sheet

| Kung ang tanong ay about... | Sagot |
|-----------------------------|-------|
| Model that generates images from noise | Diffusion Model (Stable Diffusion, Titan Image) |
| Model that understands text + images together | Large Multi-Modal Model (Claude Vision, Nova Pro) |
| Model that generates text/code | Large Language Model / LLM |
| Model that converts text to vectors | Embedding Model (Titan Embeddings) |
| Two networks competing (generator vs discriminator) | GAN (Generative Adversarial Network) |
| Architecture behind modern AI (attention mechanism) | Transformer |
| Ready-made foundation models via API | Amazon Bedrock |
| Custom ML model training | Amazon SageMaker |
| Reducing hallucination | RAG / Bedrock Knowledge Bases |
| Content safety filtering | Bedrock Guardrails |
| Making model learn new domain permanently | Fine-tuning |
| Quick behavior adjustment without training | Prompt engineering |
| Grounding responses in company documents | RAG |
| Measuring summarization quality | ROUGE score |
| Measuring translation quality | BLEU score |
| Converting text to vectors for search | Embeddings (Titan Embeddings) |
| AI coding assistant | Amazon Q Developer |
| Enterprise search with AI | Amazon Kendra |
| Chatbot building | Amazon Lex |
| Image/video analysis | Amazon Rekognition |
| Document text extraction | Amazon Textract |

---

**Bottom line para sa exam:** Alam mo yung **model types** (LLM, Diffusion, Multi-Modal, Embedding, GAN), alam mo kung **kailan Bedrock vs SageMaker**, alam mo yung **inference parameters**, alam mo yung **difference ng prompt engineering vs RAG vs fine-tuning**, at alam mo kung **anong service ang gagamitin per use case** — pasado ka na. 🎯
