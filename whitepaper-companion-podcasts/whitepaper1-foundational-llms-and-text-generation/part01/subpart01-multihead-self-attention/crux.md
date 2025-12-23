## Self-attention mechanism

> Self-attention helps the model connect the right words together.

> Self-Attention = Every word looks at every other word

> Each character looks around the group and asks: “Which of the other words are important for understanding me?”

> Self-attention is basically a conversation between words where each word decides which other words matter to it.

## Q K V

> Query : what word is asking for?

> Key : A label representing each word.

> Value : Information each word carries.

> Self-attention = Query compares itself with all Keys to find relevant Values.

## Attention Weight

> The model calculates how well each Query matches each Key.

> high score → this word is very relevant

> low score → not relevant

## Mutli-Head

> One attention head = one way of looking at relationships.

> But meaning in language is complex.

> Each head learns a *different kind of relationship*.

> Then all heads are combined to form a rich understanding.

## Summary

> Self-attention lets every word understand its relationship to every other word, and multi-head attention lets the model understand many different types of relationships at the same time.

> Multiple heads combined = deep understanding of the whole sentence