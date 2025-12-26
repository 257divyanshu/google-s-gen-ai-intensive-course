# System, Role, and Contextual Prompting

Beyond zero shot and few shot prompting, the whitepaper introduces three additional techniques that give you more control over how an LLM behaves. These methods are especially valuable in Kaggle workflows where accuracy, structure, and clarity matter. Each technique focuses on a different way of guiding the model toward more reliable and relevant output.

---

# System Prompting

System prompting sets the overarching purpose or global instructions for the model. It defines the high level intent before any task specific details. You can think of it as establishing the operating environment in which the model will work.

For example, you can use a system prompt to tell the model:
"You are a helpful and efficient coding assistant for a Kaggle data scientist."

You can also use system prompts to enforce structural constraints. A common use case in Kaggle is to instruct the model to always return predictions or intermediate results in a JSON object with predefined keys. Clear structure is essential for debugging, analysis, and submission file creation.

The paper highlights that system prompts can reduce formatting errors and keep outputs consistent by setting expectations upfront.

### Deep dive into

* Designing system prompts for predictable output formats
* Using system prompts to enforce schema validation
* System prompt templates for Kaggle workflows

---

# Role Prompting

Role prompting assigns the model a specific persona or identity. The persona influences tone, style, and even the reasoning approach the model adopts. This is useful when you need responses crafted from a particular perspective.

For example, if you are generating documentation for your Kaggle notebook, you might ask the model to act as a senior software engineer, a technical writer, or another relevant professional. The identity you assign shapes the quality and clarity of the generated content.

Role prompting can also be used creatively. You might want a friendly and humorous tone for explanations or a strict and formal voice for competition write ups. The key idea is that the role provides direction for how the model should express itself.

### Deep dive into

* Role selection for different Kaggle tasks
* Tone control using role prompts
* Persona driven documentation generation

---

# Contextual Prompting

Contextual prompting focuses on giving the model all relevant background information needed to understand the task clearly. This includes the exact input data, error messages, library versions, and any other details that influence the problem.

If you ask an LLM to debug your code, you should provide the exact snippet, the full error message, and a description of the environment you are working in. The more specific the context, the more targeted and useful the model’s output will be.

This technique is especially valuable for Kaggle challenges, where small implementation details often make the difference between success and failure.

### Deep dive into

* Structuring context for debugging prompts
* Balancing too little versus too much context
* Using contextual prompts for reproducible workflows