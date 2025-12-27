That is the single most important practical difference between the two. The answer lies in **how they calculate error** during training.

Here is the "Crystal Clear" explanation of the **Why**.

### 1. Why CBOW is better for Common Words (The "Smoothie" Effect)

**The Mechanism:**
Remember the wiring? CBOW takes all the context words (e.g., "The", "cat", "sat", "on") and **sums (or averages)** them into one single vector before trying to predict the target ("mat").

**The "Why":**
* **Averaging Dilutes Information:** When you average vectors together, you are smoothing out the data. You are finding the "general gist" of the sentence.
* **For Common Words:** This is great! Common words (like "the", "good", "water") appear in millions of noisy contexts. Averaging helps the model ignore the noise and find the stable, "average" meaning.
* **For Rare Words (The Problem):** Imagine a rare word like **"Defenestration"** (throwing someone out a window). If CBOW sees this in a sentence, it mixes "Defenestration" with common words like "the" and "he." The specific, sharp meaning of "Defenestration" gets **drowned out** by the average of the common words around it. It's like putting one drop of hot sauce into a gallon of milk—you lose the flavor.

**Summary:** CBOW treats context as a "soup." Common words taste good in soup; rare, delicate ingredients get lost.

---

### 2. Why Skip-Gram is better for Rare Words (The "Spotlight" Effect)

**The Mechanism:**
Skip-Gram works in reverse. It takes the target word (e.g., "Defenestration") and tries to predict the neighbors **one by one**. It creates separate training pairs for every context word:
1.  (Defenestration, He)
2.  (Defenestration, committed)
3.  (Defenestration, through)
4.  (Defenestration, window)

**The "Why":**
* **Individual Attention:** The model is forced to learn the relationship between "Defenestration" and "window" **specifically**. It does not average "window" with "he."
* **More Training Signal:** Even if "Defenestration" only appears **once** in your entire dataset, Skip-Gram forces the model to update the vector for "Defenestration" **4 separate times** (once for each neighbor).
* **Result:** This heavy "spotlight" ensures that even rare words get a strong, detailed vector representation because they aren't competing with or being averaged against other words.

**Summary:** Skip-Gram treats every context word as a separate conversation. Even if you rarely speak, if you have 5 one-on-one conversations, people will remember you better than if you just yelled once in a crowd.

---

### The "Classroom" Analogy

* **CBOW:** The teacher asks the **whole class** (Context) to shout the answer together. The teacher hears the "average" sound. If one quiet kid (Rare Word) says something unique, they get drowned out by the noise of the class.
    * *Result:* Good for understanding the general mood of the class (Common Words). Bad for hearing the quiet kid.

* **Skip-Gram:** The teacher asks **one student** (Target) to go around and explain the answer to **5 other students individually**. Even if that student is shy and rarely speaks, they get 5 separate chances to prove they know the answer.
    * *Result:* Great for understanding exactly what that specific student knows (Rare Words).

### Which one should you use?
* **Use CBOW if:** You have a huge dataset and care about speed (it's faster because it averages math).
* **Use Skip-Gram if:** You have a smaller dataset or need to accurately understand rare/technical terminology (medical, legal, scientific texts).