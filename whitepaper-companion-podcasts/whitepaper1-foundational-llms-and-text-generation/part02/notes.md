# **Evolution of LLMs & the Rise of Mixture-of-Experts (Part 2)**

In Part 1, we covered the foundations of Transformer-based LLMs.
Part 2 now explores **Mixture of Experts (MoE)** and then shifts into a chronological overview of how LLMs have evolved — from GPT-1 to Gemini — capturing the breakthroughs that shaped modern AI.

---

# **1. Mixture of Experts (MoE): Scaling Models Efficiently**

Modern LLMs keep getting larger, but increasing size typically increases compute costs — unless we introduce smarter architectures.
**Mixture of Experts (MoE)** is one such breakthrough.

### **How MoE Works**

* Inside one model, you have multiple **specialized “experts”** — sub-networks trained to handle different types of inputs.
* A **gating network** decides which experts should process a given token.
* Only a **small subset** of experts is activated for any particular input.

This allows a model to have billions (or even trillions) of parameters, while only using a fraction of them per forward pass — giving you “big performance at low compute cost.”

**Analogy:**
A team of specialists, with the system selecting only the experts needed for the current task.

**Deep dive into:**

* Gating strategies and routing algorithms
* Dense vs. sparse expert activation
* Challenges in training MoE models (load balancing, routing collapse)

---

# **2. The LLM Family Tree: How Models Evolved Over Time**

Transformers were introduced in 2017. After that, progress accelerated dramatically.
Here’s a timeline-based breakdown of major models mentioned in the transcript.

---

## **2.1 GPT-1 (2018) — The Unsupervised Language Learner**

GPT-1 marked a major shift because it:

* Used a **decoder-only** architecture
* Was trained **unsupervised** on a massive dataset of books (“BookCorpus”)
* Learned general language patterns purely from raw text
* Was later fine-tuned for specific tasks

### **Limitations**

* Repetition in generated text
* Poor handling of long conversations

Despite this, GPT-1 proved that unsupervised pretraining could produce versatile language understanding.

**Deep dive into:**

* What BookCorpus contained
* Why unsupervised pretraining worked so well
* Early GPT training objectives

---

## **2.2 BERT (2018) — Understanding Over Generation**

Released by Google the same year, **BERT** took the opposite approach:

* **Encoder-only**
* Focused on **understanding meaning**, not generating text
* Trained with:

  * **Masked Language Modeling (MLM)**
  * **Next Sentence Prediction (NSP)**

### **Position in the ecosystem**

* GPT-1 → good at generating but repetitive
* BERT → great at comprehension but can't hold a conversation

**Deep dive into:**

* Why BERT can't do left-to-right generation
* How MLM improves contextual understanding

---

## **2.3 GPT-2 (2019) — Scaling Up & Zero-Shot Learning**

GPT-2 took GPT-1’s decoder-only approach and massively scaled it:

* Much larger dataset (“WebText,” scraped from Reddit-linked pages)
* Many more parameters
* Much stronger coherence and long-range understanding

### **Key Breakthrough**

**Zero-shot learning**
GPT-2 could perform tasks simply by reading an example in the prompt — no fine-tuning needed.

**Deep dive into:**

* How scaling improves emergent abilities
* Early concerns about releasing GPT-2 to the public

---

## **2.4 GPT-3 (2020) — Few-Shot Mastery**

GPT-3 introduced true “massive-scale” LLMs:

* **175 billion parameters**
* Excellent **few-shot** capabilities (learn tasks from just a few examples)

This era also saw:

* **Instruction-tuned models** (e.g., InstructGPT)
* Early models specializing in code understanding and generation

GPT-3.5 and GPT-4 further improved reasoning, coding, and modality support.

### **GPT-4**

* A **multimodal** model (text + images)
* Huge **context window growth**

**Deep dive into:**

* What changed between GPT-3, 3.5, and 4
* Why instruction tuning dramatically improves alignment

---

# **3. Parallel Advances Outside OpenAI**

The transcript highlights major contributions from Google and DeepMind as well.

---

## **3.1 Google LaMDA (2021) — Built for Conversation**

LaMDA was optimized for **natural dialogue**:

* Conversational tone
* Coherence across long back-and-forth interactions

Where GPT models were becoming general-purpose, LaMDA specialized in fluid conversation.

**Deep dive into:**

* Dialogue-oriented training data
* Safety and groundedness challenges

---

## **3.2 DeepMind Gopher (2021) — Knowledge-Heavy Tasks**

Gopher was another large decoder-only model, but DeepMind focused on:

* **High-quality training data (“MassiveText”)**
* **Advanced optimization techniques**

### **Strengths**

* Excellent at **knowledge-intensive tasks**

### **Weakness**

* Still struggled with deeper **reasoning tasks**

This showed that simply adding parameters isn’t enough for all problems.

**Deep dive into:**

* MassiveText dataset design
* Why reasoning doesn’t always scale with size

---

## **3.3 Google GLaM (2021–2022) — MoE Efficiency in Action**

GLaM applied the same Mixture of Experts idea discussed earlier:

* Comparable or better performance than dense models like GPT-3
* But with **much lower compute requirements**

A key moment proving MoE was practical at scale.

**Deep dive into:**

* GLaM routing mechanism
* How it reduced training costs

---

## **3.4 DeepMind Chinchilla (2022) — The Scaling Laws Revolution**

Chinchilla challenged the “bigger is better” assumption.

### **Key finding**

For a fixed compute budget:
**Models were under-trained on data.**
Chinchilla (70B parameters) trained on *much more data* and outperformed models that were much larger.

This shifted the LLM field toward **data-optimized scaling** instead of parameter-optimized scaling.

**Deep dive into:**

* Chinchilla’s scaling law formula
* Data vs. parameters tradeoff

---

## **3.5 Google PaLM & PaLM 2 (2022–2023)**

PaLM (2022):

* Scaled efficiently using Google’s **Pathways** system
* Strong performance across a wide range of benchmarks

PaLM 2 (2023):

* Better at reasoning, coding, and math
* Surprisingly: **smaller** than PaLM 1, yet **stronger**

It became the backbone of many Google Cloud AI tools.

**Deep dive into:**

* Pathways architecture overview
* Why PaLM 2 outperformed a larger predecessor

---

## **3.6 Google Gemini (2023–2025) — Multimodal from Day One**

Gemini models are designed for multimodality from the start:

* Text
* Images
* Audio
* Video

They also:

* Scale extremely efficiently on TPUs
* Use MoE in some variants
* Come in multiple sizes: **Ultra, Pro, Nano, Flash**

### **Gemini 1.5 Pro**

Its standout feature is a **massive context window** — able to handle **millions of tokens**, enabling tasks previously impossible.

**Deep dive into:**

* TPU optimizations for LLMs
* How million-token context windows work
* Comparison of Gemini Ultra vs Pro vs Flash

---

# **Summary of Part 2**

Part 2 takes us through:

* **Mixture of Experts (MoE)** and how it makes huge models efficient
* A chronological evolution of major LLM families:

  * GPT-1 → GPT-4
  * BERT
  * LaMDA
  * Gopher
  * GLaM
  * Chinchilla
  * PaLM & PaLM 2
  * Gemini

This section shows that the LLM field is shaped not just by increasing model size, but by innovations in training data, architecture, and specialization.
