# From Bags of Words to Document Vectors

*Based on the "Embeddings and Vector Stores" Whitepaper (Feb 2025)*

While word embeddings are powerful, we often need to understand the meaning of larger chunks of text—like paragraphs or entire documents. The whitepaper traces the evolution of **Document Embeddings** from early statistical models to modern neural approaches.

## 17. The Bag-of-Words Era: LSA and LDA
The earliest approaches treated a document as a literal "bag of words"—a jumbled collection where the order didn't matter, only the content.

**LSA (Latent Semantic Analysis)**
* **The Mechanism:** It builds a matrix of word counts per document. It then applies **Dimensionality Reduction** (math similar to what we discussed in Matrix Factorization) to squash this matrix.
* **The Goal:** To uncover "hidden" (latent) semantic relationships. It tries to find the underlying themes that connect words and documents.

**LDA (Latent Dirichlet Allocation)**
* **The Mechanism:** A more probabilistic approach. It assumes every document is a mixture of various "topics."
* **The Analogy:** Think of a document as a **recipe**.
    * The **Topics** are the flavors (e.g., "Salty", "Sweet", "Spicy").
    * The **Words** are the ingredients.
    * LDA figures out the probability that a specific word belongs to a specific topic.

> **Deep Dive into:**
> * Singular Value Decomposition (SVD) in LSA.
> * Dirichlet Distributions and Bayesian Inference.
> * Topic Coherence metrics.

## 18. Statistical Weighting: TF-IDF and BM25
The transcript highlights that not all words are created equal. Words like "the" appear everywhere but mean little.

**TF-IDF (Term Frequency - Inverse Document Frequency)**
This statistical method weighs words based on a balance:
1.  **TF:** How frequently does the word appear in *this* document? (More is better).
2.  **IDF:** How frequently does it appear in the *entire* corpus? (More is bad).
* *Result:* Words that are rare globally but frequent locally get the highest score (e.g., "mitochondria" in a biology paper).

**BM25 (Best Matching 25)**
The whitepaper highlights BM25 as a "really strong Baseline." It is an advanced version of TF-IDF used heavily in search engines. It fixes issues like document length bias (preventing long documents from winning just because they have more words).

> **Deep Dive into:**
> * The BM25 ranking formula (k1 and b parameters).
> * Stop-word removal.
> * Inverted Indices in search engines.

## 19. Doc2Vec: Adding Context
The limitation of all methods above (LSA, LDA, TF-IDF) is that they **ignore word order**. "The dog bit the man" and "The man bit the dog" look exactly the same to a bag-of-words model.

**Doc2Vec (Paragraph Vectors)**
Inspired by Word2Vec, this model fixes the order problem.
* **The Innovation:** It adds a "Paragraph Vector" to the standard Word2Vec model (visualized in **Figure 7** of the whitepaper).
* **How it works:** When training to predict the next word, the model looks at the context words *plus* a special ID representing the document itself.
* **The Result:** This document ID learns a vector that represents the "theme" or "meaning" of the whole text chunk.

**Implementation:**
The whitepaper's "Snippet 4" shows how to implement this using the **Gensim** library, proving it acts very much like Word2Vec but for whole documents.

> **Deep Dive into:**
> * Distributed Memory (PV-DM) vs. Distributed Bag of Words (PV-DBOW).
> * Inference on unseen documents with Doc2Vec.