> Deep neural networks forget, get unstable, or stop learning as they get deeper.

> Residual Connections and Layer Normalization try to solve this problem.

# 1️⃣ **Residual Connections**

### 🧠 **Analogy**
> Layers in a model ~ People in a telephone game

> Signal travelling through the layers ~ Message being whispered through people

> Signal gets weak ~ Message gets ruined

### 🗒️ Points

> Residual Connection says : take the input of a layer and add it directly to its output

> It's like saying : even if this layer transforms the information badly, keep the original information safe and add it back.

> We keep the original data flowing through the network, so important information never disappears.

### 🚀 **Residuals**

* Prevent “vanishing” information
* Help deep networks learn faster
* Make training more stable
* Allow very deep LLMs (100+ layers!)

### ⭐ In One Line

> Residual Connections keep information flowing through the network and prevent deep networks from forgetting.

---

# 2️⃣ **Layer Normalization**

> Keeps the layer’s activity levels balanced.

> If a layer produces extremely large numbers or some extremely tiny numbers the next layer gets confused.

###  🧠 Analogy

> Model processing ~ Cooking curry

> Each layer's output ~ Each ingridient that is added

> Layer's output shouldn't be some extreme value ~ Ingridient's amount shouldn't be too much or too less

> Else next layer gets confused ~ Else next step in recipe breaks

> Layer Normalization is like tasting the curry each time an ingridient is added and adjusting the flavors to stay in balance

### 🗒️ Points

> Layer Normalization keeps the numbers coming out of each layer at a stable, predictable scale.

> Stable scale → easier for the model to learn → better final performance.

### ⭐ In One Line

> Layer Normalization keeps the “intensity” of information stable and prevents extreme values from breaking learning.

---

# 🎯 **Why Transformers Need Both**

> Transformers stack many many layers.

> Without **Residual Connection**  → information would vanish!

> Without **Layer Normalization** → training would explode or become unstable!

> Together they allow massive networks to train efficiently.

---

# 🔥 **One-Sentence Summary**

> **Residual connections keep information alive through deep networks, and layer normalization keeps the network stable so it doesn’t get confused by extreme values.**

