# The Lifecycle of Text: From Tokens to Word Embeddings

*Based on the "Embeddings and Vector Stores" Whitepaper*

Having established *how* to measure embedding quality, the whitepaper shifts focus to *types* of embeddings. The most common starting point for Natural Language Processing (NLP) is **Text Embeddings**.

## 12. The Pre-Processing Lifecycle: Tokenization
Before text becomes a vector, it must go through a specific lifecycle.
1.  **Tokenization:** The text string is broken down into smaller, meaningful units called "tokens." These can be whole words, sub-word units (like "word pieces"), or even individual characters.
2.  **ID Assignment:** Each unique token in the dataset is assigned a unique numerical ID. Effectively, this replaces words and punctuation with a stream of numbers.
3.  **One-Hot Encoding:** The whitepaper mentions this as a basic way to represent these IDs as binary vectors (illustrated in "Snippet 2"). However, it notes a critical flaw: raw IDs and One-Hot vectors **do not capture semantic relationships**.

> **Deep Dive into:**
> * Byte Pair Encoding (BPE) and WordPiece tokenization.
> * Sparse vs. Dense representations.
> * The curse of dimensionality in One-Hot Encoding.

## 13. Word Embeddings: "The Company It Keeps"
To solve the lack of meaning in One-Hot encoding, we use **Word Embeddings**. These are dense, fixed-length vectors designed to capture how words relate to each other semantically.

The core principle, particularly for models like **Word2Vec**, is based on the idea that *"You shall know a word by the company it keeps."* In other words, a word's meaning is determined by the context words that surround it.

**Word2Vec Architectures (Figure 5)**
The whitepaper details two main approaches within Word2Vec:
* **CBOW (Continuous Bag of Words):** Tries to predict a *target* word based on the surrounding *context*.
    * *Pros:* Faster to train; works well for common words.
* **Skip-gram:** Does the opposite—uses a *target* word to predict the surrounding *context*.
    * *Pros:* Better for infrequent words and smaller datasets.

> **Deep Dive into:**
> * The Softmax function in neural networks.
> * Negative Sampling vs. Hierarchical Softmax.
> * Handling "Out of Vocabulary" (OOV) words.

## 14. Subword Information: FastText
The transcript highlights **FastText** as an extension of Word2Vec. Its key innovation is taking into account the internal structure of words at the **sub-word level**. This allows for a more granular understanding of meaning, especially for complex words or typos.

> **Deep Dive into:**
> * Character n-grams.
> * Morphological richness in languages (e.g., German, Turkish).

## 15. Capturing the "Big Picture": GloVe and Swivel
A limitation of Word2Vec is that it focuses on "local" relationships—a small window of context words. The whitepaper introduces models that try to capture **Global** information.

**GloVe (Global Vectors)**
GloVe builds a **Co-occurrence Matrix**, which counts how often every word appears near every other word across the *entire* dataset. It then uses **Matrix Factorization** to learn vectors that encode these global patterns.

**Swivel**
Like GloVe, Swivel uses a co-occurrence matrix but is optimized for **distributed processing**, making it highly efficient for very large datasets.

> **Deep Dive into:**
> * Matrix Factorization techniques (like SVD).
> * Pointwise Mutual Information (PMI).
> * Distributed computing for ML (Sharding).

## 16. Visualization and Implementation
To prove that these numbers actually represent meaning, "Snippet 3" in the whitepaper demonstrates how to load pre-trained Word2Vec and GloVe embeddings using the **Gensim** library.

It suggests using **t-SNE** to project these high-dimensional vectors into a 2D space (visualized in **Figure 6**). In this visual space, you can actually see semantic relationships—similar words cluster together based on their proximity.

> **Deep Dive into:**
> * t-SNE (t-Distributed Stochastic Neighbor Embedding) vs. PCA.
> * UMAP (Uniform Manifold Approximation and Projection).
> * The Gensim Python library ecosystem.