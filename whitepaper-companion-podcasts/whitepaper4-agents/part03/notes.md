## Part 3: The Hands of the Agent – Tools and Knowledge

In Part 2, we explored how the agent *thinks*. Now, we look at how it *acts*.

As noted in the podcast, a Language Model without tools is like a library with the doors locked—it has great information inside, but it can't interact with the world outside. **Tools** are the bridge that connects the model's internal reasoning to external systems, APIs, and real-time data.

The transcript highlights three specific categories of tools (specifically within the Google/Vertex AI ecosystem, though the concepts apply broadly): **Extensions**, **Functions**, and **Data Stores**.

---

### 1. Extensions: The "Plug-and-Play" Connector

Extensions are the standardized way to connect an agent to an API. They are designed to be easy for the agent to use without the developer needing to write complex custom logic for every single step.

* **How they work:** The extension wraps an API (like Google Flights or a Code Interpreter). The agent is given examples of how to use it. When a user asks a question, the agent figures out which extension to call and executes it **on the agent's side** (server-side).
* **The "Code Interpreter" Example:** The transcript highlights a Code Interpreter extension. If you ask, "Calculate the Fibonacci sequence," the model doesn't just guess the numbers. It writes a Python script, uses the extension to execute that script, and returns the *actual* computed result.
* **Key Benefit:** Simplicity. The agent handles the complexity of the API call.

### 2. Functions: The "Power User" Tool

Functions are similar to Extensions—they both help the agent get things done—but with a major twist: **Execution happens on the Client Side.**

* **How they work:** The agent *does not* call the API directly. Instead, it acts as a consultant. It says, "Hey App, you should call the 'GetWeather' function with the parameter 'London'." The application (the client) then receives this instruction, makes the actual API call, and feeds the result back to the agent.
* **Why use them?**
* **Security:** You might not want the AI cloud service to have your private API keys or database credentials. The client handles the sensitive part.
* **Control:** You can process the data before giving it back to the agent (e.g., formatting a messy JSON response into a clean summary).
* **Asynchronous Tasks:** Good for long-running processes where you don't want the agent hanging while waiting for a response.



> **Analogy:**
> * **Extensions:** You ask a waiter to bring you a steak. The waiter goes to the kitchen, gets it, and brings it back. (The agent does the work).
> * **Functions:** You look at the menu and tell the waiter what you want. The waiter writes it down and hands the ticket to *you*, and you have to walk to the kitchen window to hand it to the chef. (The client does the work based on the agent's instructions).
> 
> 

---

### 3. Data Stores & RAG: The "Infinite Memory"

The third piece of the puzzle addresses the "Knowledge Cutoff" problem. Standard models only know what they were trained on. **Data Stores** allow agents to read "new books" instantly.

* **Vector Databases:** The transcript emphasizes using **Vector Databases**. Unlike a standard keyword search (Ctrl+F), a vector database stores the *meaning* of text as numbers (embeddings). This allows the agent to find information that is *conceptually* related, even if the exact keywords don't match.
* **RAG (Retrieval Augmented Generation):** This is the workflow that uses Data Stores.
1. **User asks:** "What is our company's vacation policy?"
2. **Retrieve:** The agent searches the Data Store (Company Handbook PDF) for relevant paragraphs.
3. **Augment:** It pastes those paragraphs into the model's instructions (invisible to the user).
4. **Generate:** The model answers the question using that specific, fresh data.



**👇 Deep dive into:**

* *OpenAPI Specifications (Swagger)* – The standard format used to "teach" agents what an API can do (inputs/outputs).
* *Semantic Search vs. Keyword Search* – Why "King - Man + Woman = Queen" is the classic example of how vectors understand relationships.

---

### Summary of Part 3

We have equipped our agent with **Extensions** for easy API access, **Functions** for secure, controlled actions, and **Data Stores** (via RAG) to access real-time knowledge.

Now that we have a fully functional agent—Brain (Part 1), Logic (Part 2), and Hands (Part 3)—how do we actually build one that doesn't break?

**Coming up next in Part 4:** We conclude with **Building and Training**. We will explore the trade-offs between **In-Context Learning** and **Fine-Tuning**, and look at a practical "Quick Start" using the popular **LangChain** framework.