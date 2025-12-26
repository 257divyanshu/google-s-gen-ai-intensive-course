# Core Prompt Engineering Techniques

After understanding output configuration, the next major focus is the set of techniques that help you shape model predictions. Clear prompt construction is the baseline, but applying the right prompting methods can significantly enhance the quality and reliability of an LLM's output. The whitepaper highlights several foundational approaches that are easy to apply and powerful in Kaggle workflows.

---

# Zero Shot Prompting

Zero shot prompting is the simplest form of prompting. You provide the model with a task description and the necessary input, but you do not include any examples. The model relies solely on its pretraining to interpret and accomplish the task.

For example, if you need a data preprocessing code snippet for a Kaggle notebook, you can describe the task and supply the relevant data. Because the model has seen massive amounts of code during training, it can often generate a reasonable response purely from the description.

The whitepaper emphasizes a critical practice here: documenting your prompts. Kaggle users iterate continuously, testing different approaches and refining ideas. A structured system for recording prompts, noting what worked, what failed, and why, is essential for long term improvement. Good prompt documentation becomes part of your competitive strategy.

### Deep dive into

* Building a prompt versioning system
* Zero shot prompting patterns that work well for code
* Strategies for crafting minimal task descriptions

---

# One Shot and Few Shot Prompting

When zero shot prompting does not produce the precision or structure you need, you can shift to one shot or few shot prompting. These techniques include one or more examples within the prompt to guide the model's output.

For instance, if your Kaggle submission requires predictions in a specific JSON format, you can show the model an example of input data and the exact JSON output you expect. The model then uses these examples to infer both the structure and the task logic.

This approach is extremely useful for tasks such as:

* Converting raw data into a required output format
* Extracting specific fields from text or tabular data
* Ensuring the model respects strict formatting or schema rules

However, the paper also outlines an important caution. The quality and relevance of your examples directly influence the model's performance. Even a small mistake in an example can mislead the model. Poorly chosen examples can result in incorrect or incoherent output.

Including edge cases is equally important. Kaggle competitions often involve corner scenarios that break naive solutions. By embedding examples of these rare or unusual inputs, you can strengthen the robustness of the generated output.

### Deep dive into

* Designing effective examples for few shot prompts
* Using examples to enforce structure in generated code
* Handling edge cases through curated prompt datasets