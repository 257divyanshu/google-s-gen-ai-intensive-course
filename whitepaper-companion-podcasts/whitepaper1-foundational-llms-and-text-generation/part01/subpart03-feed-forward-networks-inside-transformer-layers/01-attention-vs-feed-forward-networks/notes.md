# 🥊 **Attention vs Feed-Forward Network (FFN)**

# 🔵 **1. What They Do**

### **Attention**

* Figures out **relationships between words**
* Every word looks at every other word
* Helps understand context

### **FFN**

* Improves each word **individually**
* No interaction between words
* Helps refine the token’s internal meaning

---

# 🔵 **2. Good Mental Model**

### **Attention = Group Discussion**

Everyone talks, shares information, understands who is important.

### **FFN = Personal Study Time**

Each student sits alone and improves their own notes using what they learned.

---

# 🔵 **3. Main Purpose**

### **Attention**

> “How should I understand other words around me?”

### **FFN**

> “How should I upgrade my own representation?”

---

# 🔵 **4. Data Flow**

### **Attention**

* Words talk to each other
* Output depends on *all* tokens

### **FFN**

* Words do NOT talk
* Each token is processed **independently**
* Same mini-network applied to every token

---

# 🔵 **5. What Information They Use**

### **Attention**

Uses:

* Query
* Key
* Value
* Attention weights
* Context from whole sentence

### **FFN**

Uses:

* Only the token’s own vector
* No Q/K/V
* No context from other tokens

---

# 🔵 **6. What They’re Good At**

### **Attention**

* Resolving references (“it” → “tiger”)
* Understanding long-range connections
* Capturing relationships, meaning flow
* Handling complex sentence structure

### **FFN**

* Creating richer features inside a token
* Transforming, amplifying, reshaping meaning
* Learning non-linear patterns
* Making the model expressive

---

# 🔵 **7. Without Them What Happens?**

### **Without Attention**

Model can’t understand:

* Context
* Who refers to whom
* Long-distance dependencies

→ It would behave like a bag of words.

### **Without FFN**

Model can’t:

* Deeply transform meaning
* Learn complex abstractions
* Refine token-level understanding

→ It becomes shallow and weak.

---

# 🔵 **8. Clean One-Line Summary**

> **Attention connects words; FFN transforms words.**

---

# 🔥 Bonus: Ultra-Short Version

* **Attention = looking around**
* **FFN = thinking deeply about yourself**
