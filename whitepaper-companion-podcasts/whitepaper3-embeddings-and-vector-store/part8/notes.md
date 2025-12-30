# The Social Fabric: Graph Embeddings

*Based on the "Embeddings and Vector Stores" Whitepaper (Feb 2025)*

The final type of embedding mentioned is perhaps the most complex because it introduces a new dimension: **Relationship**. In previous models, data points (words, images) were often treated as independent items. In **Graph Embeddings**, the connections between them are just as important as the items themselves.

## 29. Nodes, Edges, and the Network

A graph is made of **Nodes** (objects) and **Edges** (connections).

* **The Analogy:** Think of a **Social Network**.
* **Nodes:** The people.
* **Edges:** Friendships or follows.



**What the Embedding Captures**
A standard embedding might describe *who* a person is (age, location). A **Graph Embedding** captures their **position in the network**.

* Who are they connected to?
* Are they a central hub (influencer) or on the fringe?
* Who are their friends' friends?

The transcript describes this as encoding the **"Social Fabric"**—capturing the structure of the community itself within the vector.

## 30. Key Algorithms

The whitepaper lists several specific algorithms designed to walk through these networks and turn them into numbers:

1. **DeepWalk & Node2Vec:** These use "Random Walks." The algorithm pretends to be a person randomly clicking links. If two nodes are often visited in the same random walk, they are considered "close" and get similar embeddings (conceptually similar to Word2Vec).
2. **LINE (Large-scale Information Network Embedding):** Optimized for very large networks.
3. **GraphSAGE:** A more modern approach that learns to generate embeddings by sampling and aggregating features from a node's local neighborhood (inductive learning).

> **Deep Dive into:**
> * Random Walks vs. Breadth-First Search (BFS) / Depth-First Search (DFS).
> * Graph Neural Networks (GNNs) vs. Graph Convolutional Networks (GCNs).
> * Homophily vs. Structural Equivalence.
> 
> 

## 31. Applications

Why do we need this?

* **Link Prediction:** "Who might know each other?" (Facebook's "People You May Know").
* **Node Classification:** "Categorizing users" (e.g., detecting bot accounts based on who they interact with).
* **Graph-Based Recommendations:** Suggesting products not just because you like them, but because people *connected* to you like them.

---