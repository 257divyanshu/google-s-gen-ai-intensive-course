# Self Consistency

Self consistency builds upon Chain of Thought by increasing the reliability of the model’s reasoning. Instead of generating a single chain of thought, you ask the model to produce multiple different reasoning paths for the same prompt. Once you have these varied chains, you select the answer that appears most consistently across them.

This is similar to consulting several experts and choosing the consensus answer. While this approach requires more computation, it can be especially valuable for high stakes Kaggle tasks where accuracy matters, such as generating final predictions or validating complex reasoning.

### Deep dive into

* When self consistency meaningfully improves accuracy
* Tradeoffs between cost and reliability
* Methods for selecting the consensus answer

---

# Tree of Thoughts

Tree of Thoughts, often abbreviated as ToT, extends the idea behind Chain of Thought by allowing the model to explore multiple reasoning paths in a branching structure rather than a single linear chain. Instead of committing to one line of reasoning, the model can branch, test out options, and backtrack if a path turns out to be unproductive.

This mirrors how humans tackle difficult open ended problems by exploring many possibilities before deciding which direction to pursue. For challenging Kaggle tasks where the solution path is unclear, ToT can support deeper exploration and creativity.

The whitepaper notes that a comparison between CoT and ToT makes the advantages obvious. ToT enables a wider search over possible reasoning paths, making it more suitable for complex problem solving.

### Deep dive into

* When ToT is preferred over CoT
* How branching affects reasoning diversity
* Techniques for pruning unproductive branches

---

# ReAct: Reason and Act

ReAct is a technique designed for tasks where the model must combine reasoning with actions. Instead of only generating text, the model alternates between thinking and interacting with external tools. These tools might include search engines, code interpreters, or APIs.

In a Kaggle context, this can be extremely powerful. For example, the model could:

* Execute code inside a Kaggle notebook
* Inspect the output
* Use that output to decide what to do next

This creates an iterative workflow where the LLM becomes an active collaborator, not just a passive generator. The paper includes an example using LangChain and Vertex AI where the model performs a search to gather information and then uses that information to guide further reasoning.

### Deep dive into

* Designing effective ReAct loops
* Working with code interpreters in Kaggle notebooks
* Tool selection strategies for ReAct based workflows

---

# Automatic Prompt Engineering (APE)

Automatic Prompt Engineering is an advanced technique where the model helps generate its own prompts. Instead of manually writing prompt variations, you ask the LLM to create many candidate prompts for a task. You then evaluate these prompts based on their performance and select the best ones.

This method can significantly reduce manual experimentation and can uncover prompt formulations you may not have considered yourself. In a Kaggle project, APE can help improve code generation, data transformation workflows, or analysis steps by automatically discovering more effective prompting strategies.

### Deep dive into

* Methods for evaluating generated prompt variations
* Using APE for code specific tasks
* Integrating APE into iterative Kaggle pipelines