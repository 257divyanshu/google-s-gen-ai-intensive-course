# Practical Starting Points for Sampling Settings

With many sampling controls available, it can be difficult to know where to begin. The whitepaper provides several recommended configurations that serve as strong starting points for different Kaggle scenarios. These benchmarks balance coherence, creativity, and precision depending on the nature of the task.

## Balanced Creativity for General Ideation

For tasks that require coherent output with a touch of creativity, such as brainstorming model architectures or feature ideas, the paper suggests:

* Temperature around 0.2
* Top P set to 0.95
* Top K set to 30

This combination maintains clarity while still introducing enough variation to spark new ideas.

### Deep dive into

* Why mid range sampling settings maintain stability
* Using these defaults for model design discussions
* Comparing ideation outputs across sampling configurations

---

## High Creativity for Novel Solutions

When you need highly inventive output, such as generating new data augmentation strategies or exploring unconventional approaches, the settings can be increased:

* Temperature around 0.9
* Top P at 0.99
* Top K at 40

These values expand the model's creative freedom and allow it to explore more unexpected or unusual options.

### Deep dive into

* Identifying good use cases for high randomness
* Creative exploration without losing direction
* How high sampling values influence algorithm brainstorming

---

## Low Creativity for Accuracy and Reliability

For tasks requiring correctness and stability, such as generating boilerplate code or producing factual, predictable answers, you should reduce the randomness:

* Temperature around 0.1
* Top P at 0.9
* Top K at 20

This configuration produces focused, controlled outputs that minimize errors.

### Deep dive into

* When low randomness prevents code hallucinations
* Testing and validating generated code
* Prompt techniques that pair well with low sampling

---

## Single Correct Answer Scenarios

Some tasks demand a single definitive answer, such as implementing a specific algorithm or writing a deterministic block of code. In these situations, the paper recommends:

* Temperature set to zero

This forces the model to always pick the most probable next word, removing all randomness. It is ideal for precision focused Kaggle work.

### Deep dive into

* Risks of zero temperature in longer generations
* How to design prompts for deterministic outputs
* Debugging deterministic model mistakes

---

# The Repetition Loop Bug

The paper also warns about a common issue called the repetition loop bug. This is a situation where the model becomes stuck repeating the same phrases or patterns. The problem can occur at both ends of the sampling spectrum.

* At low temperatures, the model becomes too predictable and can cycle through the same few next word choices.
* At high temperatures, randomness can coincidentally push the model back into earlier states, creating unexpected loops.

The solution is to fine-tune temperature, top K, and top P to avoid extremes. The ideal configuration provides enough variation to prevent repetition while maintaining enough structure to avoid chaotic loops.

### Deep dive into

* Identifying repetition loops in generated output
* Sampling adjustments that reduce looping behavior
* How model context window length influences repetition