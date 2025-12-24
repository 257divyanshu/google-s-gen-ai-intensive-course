# 🗒️ Points

> Transformers are built from **repeated blocks**.

> Each layer of transformer has **two major parts** : **Self-Attention** & **Feed-Forward Network**

> The Feed-Forward Networks process each word independently after attention.

> FFN (a) applies a **linear transformation** (b) applies a **non-linear activation** (c) applies **another linear transformation**

> FFNs help the model understand **more complex patterns than attention alone can capture**.

> Attention figures out the **relationships**. FFNs figures out **how to use those relationships**.

> The model needs attention to **understand the global context**.

> The model needs FFN to **transform and improve each token's internal meaning**.

> FFN is important because **attention alone is not enough**.

> After words interact using attention, the feed-forward network **enriches each word’s meaning individually**, giving the model deeper expressive power.

> Both **Attention** and **FFN** are required for powerful language understanding.

# 🧠 Analogy 1

> **Self-attention** ~ words talk to each other ~ a group discussion

> **Feed-Forward Network** ~ each word thinks on its own ~ personal reflection time

> It’s like **after the group discussion**, each student goes back to their desk and **improves their own notes**.

# 🧠 Analogy 2

> Self-attention = the artist looking at the whole scene

> FFN = the tools (brushes, colors) the artist uses to refine the painting