# Structure in Chaos: Embeddings for Databases and Recommendations

*Based on the "Embeddings and Vector Stores" Whitepaper (Feb 2025)*

While text and images are "unstructured" (messy), we also need to handle "structured" data—think Excel sheets, SQL tables, and customer records. The whitepaper notes that creating embeddings here is trickier because the meaning depends heavily on the specific **Schema** (the column names and rules).

## 27. Tabular Data and Dimensionality Reduction

For a standard table with rows and columns, the goal is to create an embedding for each **Row**.

**Technique: PCA (Principal Component Analysis)**
The transcript highlights PCA as a go-to method here.

* **The Problem:** A database row might have 50 columns (Age, Zip Code, Income, Last Login, etc.).
* **The Solution (PCA):** PCA is a mathematical technique that squashes these 50 columns down to a smaller set of "Principal Components" (e.g., 5 numbers) that capture the most variance (information) in the data.
* **Use Cases:**
* **Anomaly Detection:** Spotting weird rows (fraud) that don't fit the pattern.
* **Input Features:** Feeding these compressed vectors into other ML models.



> **Deep Dive into:**
> * Principal Component Analysis (Eigenvalues and Eigenvectors).
> * Autoencoders (Neural networks for compressing tabular data).
> * TabNet (Deep learning specifically for tabular data).
> 
> 

## 28. Recommendation Systems: Users and Items

This is where structured data shines.

* **The Goal:** Map **Users** (people) and **Items** (products/movies) into the **Same Embedding Space**.
* **The Logic:** If User A is mathematically close to Item B in the vector space, it is a "match."

**Hybrid/Rich Representations**
The most powerful systems don't just use the ID numbers. They combine:

1. **Structured Data:** (User age, Item price, Purchase history).
2. **Unstructured Data:** (User reviews, Product descriptions).
By merging these, you get a "richer" representation that understands not just *who* bought *what*, but *why*.

> **Deep Dive into:**
> * Collaborative Filtering vs. Content-Based Filtering.
> * Two-Tower Architecture (standard for modern recommender systems).
> * Graph Neural Networks (GNNs) for recommendation (e.g., GraphSAGE).
> 
> 

---