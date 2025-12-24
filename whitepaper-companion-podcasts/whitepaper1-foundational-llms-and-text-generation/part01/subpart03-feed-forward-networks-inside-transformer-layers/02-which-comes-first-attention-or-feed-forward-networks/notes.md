# ✅ **Attention comes first. FFN comes second.**

Every Transformer layer (in almost all modern LLMs) follows this order:

---

# **1️⃣ Self-Attention (or Masked Self-Attention)**

**Words talk to each other first.**
The model builds contextual meaning by comparing every word with every other word.

---

# **2️⃣ Feed-Forward Network (FFN)**

**Each word processes itself individually**, using the context gathered from attention.

---

# 💡 Why attention comes first?

Because attention gives each token a “global view” of the sentence.

Then FFN uses that global view to deeply transform each token internally.

Attention = “What is happening around me?”
FFN = “Now that I know the context, how should I update myself?”

---

# 📚 **Exact Transformer Layer Order (simplified)**

### **Step A — Attention sub-layer**

* LayerNorm
* Multi-head attention
* Residual connection

### **Step B — FFN sub-layer**

* LayerNorm
* Feed-forward network
* Residual connection

---

# 🧠 One Sentence Summary

> **First attention builds context across tokens; then FFN enriches each token individually based on that context.**