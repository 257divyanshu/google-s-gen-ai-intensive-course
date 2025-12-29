# Beyond Text: Image and Multimodal Embeddings

*Based on the "Embeddings and Vector Stores" Whitepaper (Feb 2025)*

The whitepaper moves into the visual world, explaining how machines "see" and how they connect vision with language.

## 24. How Image Embeddings Work

Just as we convert text into numbers, we can convert images into vectors. The transcript highlights two main architectures for this:

**1. Convolutional Neural Networks (CNNs)**

* **The Mechanism:** CNNs process images through layers. Early layers detect simple lines and colors. Deeper layers detect complex shapes and objects (eyes, wheels, leaves).
* **The "Embedding":** We don't use the final output (which just says "This is a Cat"). Instead, we take the **activations from the later layers**—the rich numerical data representing the "learned features" just before the final decision is made.
* *Analogy:* It’s like taking a chef’s detailed tasting notes (the embedding) rather than just the final menu item name.

**2. Vision Transformers (ViTs)**

* **The Mechanism:** Inspired by text models like BERT. ViTs chop an image into small square "patches" (like puzzle pieces). They treat these patches exactly like words in a sentence, using **Self-Attention** to understand how the patches relate to each other globally.

> **Deep Dive into:**
> * ResNet and EfficientNet architectures (CNNs).
> * The "Patchify" process in Vision Transformers.
> * CLIP (Contrastive Language-Image Pre-training) loss functions.
> 
> 

## 25. Multimodal Embeddings: Bridging the Gap

A "Multimodal" embedding is a joint representation. It maps **Text** and **Images** into the **same** vector space.

* **The Goal:** To make the vector for an image of a dog mathematically similar to the vector for the text "A photo of a dog."
* **Vertex AI Implementation:** The whitepaper's "Snippet 6" demonstrates using the Google Vertex AI API to generate these joint embeddings, allowing you to search for images using text queries.

## 26. ColPali: The "OCR Killer"

The transcript mentions a revolutionary model called **ColPali** (phonetically transcribed as "Cali" or "kpali").

* **The Problem:** Traditionally, to search a PDF with charts and images, you first had to use **OCR** (Optical Character Recognition) to turn it into raw text, often losing the layout and visual info.
* **The ColPali Solution:** It is a **Vision-Language Model** that treats the *entire document page* as an image.
* **The Magic:** It generates embeddings based on the visual screenshot of the page. This allows it to "read" charts, tables, and diagrams visually, just like a human does, without ever converting them to text first.

> **Deep Dive into:**
> * Visual Document Retrieval (VDR).
> * Late Interaction models (ColBERT strategy applied to images).
> * Benchmarks like **ViDoRe** (Visual Document Retrieval).