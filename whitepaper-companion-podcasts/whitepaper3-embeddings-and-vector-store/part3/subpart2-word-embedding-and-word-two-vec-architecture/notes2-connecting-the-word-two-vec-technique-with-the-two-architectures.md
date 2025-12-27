Here is the exact relationship:

1.  **Word2Vec** is the **"Family Name"** (or the technique).
2.  **CBOW** and **Skip-Gram** are the **Specific Architectures** (the actual blueprints).

Word2Vec is the *methodology*. It doesn't have just one architecture; it has **two distinct architectures** that you can choose from.

### The "Wiring" Difference
This is where the connection happens. Both architectures use a Neural Network with 3 layers (Input, Hidden, Output), but the **wiring** is different.

**1. The CBOW Architecture**
* **The Wiring:** It connects **multiple** input neurons (context words) to **one** output neuron (target word).
* **What happens inside:** The inputs get smashed together (summed/averaged) before hitting the hidden layer.
* *Analogy:* Several witnesses (Context) trying to identify one suspect (Target).

**2. The Skip-Gram Architecture**
* **The Wiring:** It connects **one** input neuron (target word) to **multiple** output neurons (context words).
* **What happens inside:** One input triggers multiple separate predictions at the output.
* *Analogy:* One suspect (Target) trying to identify their several accomplices (Context).

### Summary:

Both CBOW and Skip-Gram—despite their different wiring—have that same **Hidden Layer** in the middle. When training is done, we throw away the input and output layers for *both* of them. We only keep that middle Hidden Layer, which becomes the **Lookup Table**.