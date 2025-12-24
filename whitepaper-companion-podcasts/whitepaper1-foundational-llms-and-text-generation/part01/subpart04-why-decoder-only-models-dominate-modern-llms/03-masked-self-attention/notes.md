# 🧠 **Why Do We Need Masked Self-Attention?**

Decoder-only models **generate text one token at a time**.

Example: generating the sentence

> “The cat sat down.”

The model generates:

1. “The”
2. “The cat”
3. “The cat sat”
4. “The cat sat down”
5. …

At step 3, the model should **not** be allowed to look at “down”
— because it hasn’t generated it yet.

So we must **hide future words** from the model during training.

That hiding = **masking**.

---

# 🎭 **Masked Self-Attention = Hiding the future from the model**

Imagine this table showing which words can “look at” which:

| Position | Can See | Cannot See    |
| -------- | ------- | ------------- |
| Token 1  | itself  | tokens 2,3,4… |
| Token 2  | 1,2     | tokens 3,4…   |
| Token 3  | 1,2,3   | tokens 4,5…   |
| Token 4  | 1,2,3,4 | tokens 5,6…   |

The model is **allowed** to see only the tokens *before* it.
Future tokens are **blocked** (masked).

---

# 🔒 **What does masking look like inside the model?**

Inside self-attention, every pair of tokens forms an attention score:

For token *i* attending to token *j*:

* if j ≤ i → allowed
* if j > i → forbidden (masked)

Forbidden means:

> The score is replaced with **−∞** (or a very large negative number).

So after softmax, the “future token” gets **zero attention**.

---

# 👁️ **Intuitive Example**

Sentence:

> “The tiger drank water”

When generating “tiger”, the model can see:

* “The”

But it cannot see:

* “drank”
* “water”

Because those happen in the future.

If it could see “drank water”, it would be cheating.
Masked attention prevents cheating.

---

# 🧩 **Why masking matters:**

### ✔️ Prevents cheating during training

The model must *learn* to predict next tokens from **prior context only**.

### ✔️ Supports auto-regressive generation

Masked self-attention mirrors actual generation behavior.

### ✔️ Enables chain-of-thought reasoning

Each new token builds on all previous ones.

---

# 🔥 **Masked vs Unmasked Self-Attention**

| Architecture | Attention Type | Meaning                            |
| ------------ | -------------- | ---------------------------------- |
| **Encoder**  | Unmasked       | Every token sees every other token |
| **Decoder**  | Masked         | Each token sees only past tokens   |

---

# 🧠 **Masked Self-Attention in ONE sentence**

> **Masked self-attention hides future tokens, ensuring the model only uses past information while generating text.**
