# Stepback Prompting

Stepback prompting is introduced as a technique that helps the model deliver more insightful and well grounded answers by first guiding it to think more broadly. Instead of diving straight into a narrow Kaggle task, you first ask the model a more general question related to the same domain. This primes the model's internal knowledge and encourages responses with better depth and perspective.

For example, if you are looking for a novel feature for a competition, you might begin by asking about general principles of feature engineering. Once the model has activated this broader knowledge, you can follow up with a prompt focused specifically on your dataset. The paper notes that this technique can also help mitigate certain biases in the model's responses.

### Deep dive into

* When stepback prompting improves idea generation
* Using broad questions to unlock domain knowledge
* Identifying tasks that benefit from priming

---

# Chain of Thought Prompting

Chain of Thought prompting, often abbreviated as CoT, is a widely discussed and highly effective technique for tasks that require multi step reasoning. Instead of asking the model to provide only the final answer, you instruct it to generate the intermediate reasoning steps that lead to the conclusion.

This approach gives you visibility into the model's thought process, helping you evaluate whether its suggestions are logically sound. The paper highlights several advantages of CoT:

* It is easy to implement.
* It works reliably with common LLMs.
* It increases transparency by revealing intermediate steps.
* It tends to improve robustness across different inputs.

There is a notable trade off. CoT requires more tokens because the model is generating both reasoning steps and the final answer, which can increase cost and processing time in a Kaggle environment.

The whitepaper provides a compelling example. When asked a math question directly, the model produces an incorrect answer. However, when prompted to think step by step, the model solves it correctly. This clearly illustrates how prompting for intermediate reasoning can improve accuracy.

The paper also describes a variation called single shot CoT. In this method, you include one example of a solved problem that demonstrates the step by step reasoning style you want. Combining this example with CoT instructions can further improve performance.

CoT is particularly valuable for Kaggle tasks that involve:

* Debugging complex code
* Understanding why a model's performance is not improving
* Documenting the logic behind generated solutions
* Generating structured or synthetic data based on reasoning

### Deep dive into

* When CoT harms performance due to verbosity
* Constructing effective step by step prompts
* Single shot CoT versus few shot CoT