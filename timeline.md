---
customTheme: cyber2
enableMenu: false


---


---


---


<!-- .slide: data-background-opacity="0.4" data-background-image="./pics/blob.gif" data-background-color="#000000" -->

## Ai 2025

---

### Purpose Disposition

My personal current understanding / world model of what currently is taking place

- trends 
- core techniques
- implications for organisations

---

<!-- .slide: data-background-opacity="0.1" data-background-image="./pics/blob.gif" data-background-color="#000000" -->

> **Calling the Ai-revolution an intelligence explosion is like calling the industralization an horse power explosion** - Tamay Besiroglu 

---

## timeline

![](./diagrams/timeline.png)

---

> The beaver told the rabbit as they stared at the Hoover Dam: No, I didn’t build it myself, but it’s based on an idea of mine.” 

---

### enablers

1. **Hardware & Compute**
   - GPU/TPU advancements.
   - Massive build up
   - Availability of infrastucture

--

![](./pics/decline-and-falll-of-computing_disk_io.png)

--

![](./pics/performance_year.png)

--

![](./pics/spendings.png)

--

![](./pics/education.png)

---

2. **Data & Corpus**
   - Massive text datasets for training
   - Not only seminal, offical texts but conversations and peoples use internet for two decades plus.

---

## Whos doing it



![](./diagrams/sectors.png)

---

![](./diagrams/by_region.png)

---

![](./diagrams/polymarket.png)

--

![](./diagrams/poly_table.png)

--

#### The Gutenberg Analogy

> "Writing has been around for long, but only when everybody reads it makes sense for a Gutenberg revolution"

- Ideas existed for decades
- Enablers made implementation possible
- Critical mass of adoption needed
- Infrastructure enables innovation

---

### Still a next token machine

--

### 1. Temperature
- Temperature controls the probability distribution of the next token.
  - **Low Temperature (e.g., 0)**: The model becomes deterministic, always choosing the most probable token. This is great for precise, factual responses.
  - **High Temperature (e.g., close to 1 or higher)**: The model introduces more randomness, making less probable tokens more likely. This boosts creativity and diversity.
- **Use Case**: Use a low temperature for tasks like answering factual questions and a high temperature for creative tasks like storytelling.


--

### 2. Top-K Sampling
- Top-K limits the model to sampling from the top K most probable tokens at each step.
  - **Low K**: Focuses on a small group of highly likely tokens, making the output more coherent but less diverse.
  - **High K**: Considers more tokens, increasing diversity but possibly reducing focus.
- **Use Case**: Ideal when you want to manually control how many token options the model considers.

--

### 3. Top-P (Nucleus) Sampling
- Top-P selects the smallest set of tokens whose combined probability exceeds a threshold P (e.g., 0.9).
  - **Low P**: Limits the selection to the most probable tokens, keeping the output focused.
  - **High P**: Includes more tokens, adding diversity and creativity.
- **Use Case**: Useful for dynamically balancing coherence and variety based on token probabilities.

--

### 4. Output Length
- This sets the maximum number of tokens the model can generate in its response.
  - **Short Length**: Keeps responses concise and efficient but may cut off detail.
  - **Long Length**: Allows detailed responses but increases computation time and cost.
- **Use Case**: Adjust this to control how verbose or brief the output should be.

---

### Prompt engineering

When you write a prompt, you are essentially trying to set up the LLM to predict the desired sequence of tokens that constitutes your answer or output. Effective prompt engineering involves understanding how the model works and then tinkering with various aspects of the prompt, such as word choice, style, tone, structure, and the context provided, to achieve the desired outcome

--

One-shot and few-shot prompting: These techniques provide the LLM with one or a few examples to demonstrate the desired output format or pattern. This helps the model understand the task better and can steer it towards a specific type of response.

1. **Zero Shot**  
   This is the simplest prompting method, where a task description and initial text are provided without any examples. The LLM relies solely on its pre-trained knowledge to produce an output, making it a "zero-shot" approach.    
   
   ```mermaid
   graph LR
   A[Prompt] --> B[Output]
   

--

2. **One-Shot & Few-Shot Prompting**  
   These techniques involve including one example (one-shot) or multiple examples (few-shot) in the prompt to demonstrate the desired output pattern or format, helping the LLM understand the task more effectively.  

   ```mermaid
   graph LR
   A[Prompt with Examples] --> B[Output]
   ```

--

System, contextual, and role prompting: These techniques allow you to set the overall context and purpose (system prompt), provide specific background information (contextual prompt), or assign a specific character or identity to the LLM (role prompt). This can influence the style, tone, and focus of the LLM's output.

3. **System Prompting**  
   This technique defines the overarching context or purpose for the LLM, such as specifying the task (e.g., classification, translation) or output format (e.g., JSON), guiding the model’s behavior at a high level.  
   
   ```mermaid
   graph LR
   A[System Instruction] --> B[Task Prompt] --> C[Output]
   ```

--

4. **Contextual Prompting**  
   Provides specific background details or task-relevant information to the prompt, enabling the LLM to tailor its response more accurately to the given scenario.  
   
   ```mermaid
   graph LR
   A[Context] --> B[Task Prompt] --> C[Output]
   ```

--

5. **Role Prompting**  
   Assigns a specific role or persona to the LLM (e.g., travel guide, teacher), directing it to generate responses consistent with that role’s perspective, tone, or expertise.  
   
   ```mermaid
   graph LR
   A[Role Assignment] --> B[Task Prompt] --> C[Output]
   ```

--

6. **Step-Back Prompting**  
   The LLM is first prompted with a general question related to the task to activate broader knowledge, then the answer is used in a subsequent prompt to address the specific task, enhancing reasoning and accuracy.  

   ```mermaid
   graph LR
   A[General Question] --> B[Answer to General Question] --> C[Specific Task Prompt] --> D[Output]
   ```


--


7. **Chain of Thought (CoT)**  
   Encourages the LLM to produce intermediate reasoning steps before delivering the final answer, improving performance on complex tasks by making the thought process explicit.  
   ```mermaid
   graph LR
   A[Prompt] --> B[Reasoning Step 1] --> C[Reasoning Step 2] --> D[Final Answer]
   ```

--

8. **Self-Consistency**  
   The LLM generates multiple responses to the same prompt using varied reasoning paths (often with higher temperature settings), then selects the most consistent answer to improve reliability.  
   ```mermaid
   graph LR
   A[Prompt] --> B[Response 1]
   A --> C[Response 2]
   A --> D[Response 3]
   B --> E[Select Most Consistent]
   C --> E
   D --> E
   E --> F[Final Output]
   ```

--

9. **Tree of Thoughts (ToT)**  
   Explores multiple reasoning paths or ideas in a branching structure, allowing the LLM to consider various possibilities before converging on a final output, useful for deliberate problem-solving.  
   ```mermaid
   graph TD
   A[Prompt] --> B[Thought 1]
   A --> C[Thought 2]
   B --> D[Subthought 1.1]
   B --> E[Subthought 1.2]
   C --> F[Subthought 2.1]
   D --> G[Final Output]
   E --> G
   F --> G
   ```

--


10. **ReAct (Reason & Act)**  
    Combines reasoning and action, where the LLM first reasons about the task and then performs an action (e.g., generating text or code) based on that reasoning, synergizing thought and execution.  
    
    ```mermaid
    graph LR
    A[Prompt] --> B[Reasoning] --> C[Action] --> D[Output]

    ```

--


11. **Automatic Prompt Engineering**  
    **Summary:** Automates the creation or optimization of prompts through an iterative process of generating prompts, evaluating responses, and refining them, reducing manual effort in prompt design.  
    **Mermaid Diagram:**
    ```mermaid
    graph LR
    A[Initial Prompt] --> B[Generate Response]
    B --> C[Evaluate Response]
    C --> D[Optimize Prompt]
    D --> A
    ```

--


12. **Code Prompting**  
    Utilizes prompts to perform code-related tasks, such as writing, explaining, translating, or debugging code, leveraging the LLM’s ability to handle programming languages.  
    
    ```mermaid
    graph LR
    A[Prompt for Code Task] --> B[Perform Code Task] --> C[Output]
    ```

---

### agents
> Ai agents are just a bunch of python scripts and an api key  

---

### Reflection


![](./diagrams/reflection.svg)

---

### Tools


![](./diagrams/tools.svg)


---

### Planning

![](./diagrams/planning.svg)


---

### Multi agent

![](./diagrams/multi_agent.svg)


---


### Example

```python
# 1. Tools - The agent's capabilities
def list_tables(reasoning: str) -> List[str]:
    """Returns a list of tables in the database."""
    # Tool implementation...

def describe_table(reasoning: str, table_name: str) -> str:
    """Returns schema information about the specified table."""
    # Tool implementation...

# 2. Agent Prompt - The agent's instructions
AGENT_PROMPT = """
<purpose>
    You are a world-class expert at crafting precise DuckDB SQL queries.
    Your goal is to generate accurate queries that exactly match the user's data needs.
</purpose>

<instructions>
    <instruction>Use the provided tools to explore the database...</instruction>
    <instruction>Think step by step about what information you need.</instruction>
</instructions>
"""

# 3. Main execution
def main():
    # Initialize agent
    # Process user input
    # Execute tools based on reasoning
```

---

### MCP

> provides a structured way to connect AI agents with external tools

--

### Google Maps MCP

```python
# MCP Protocol Definition
maps_geocode = {
    "input": "address (string)",
    "returns": ["location", "formatted_address", "place_id"]
}

maps_reverse_geocode = {
    "inputs": {
        "latitude": "number",
        "longitude": "number"
    },
    "returns": ["formatted_address", "place_id", "address_components"]
}

maps_search_places = {
    "inputs": {
        "query": "string",
        "location": "optional: { latitude: number, longitude: number }",
        "radius": "optional: number (meters, max 50000)"
    },
    "returns": "array of places with names, addresses, locations"
}

```

--

## A2A

> provides as structured way to connect AI agents with other AI agents

--

```json
{
  "name": "Weather Agent",
  "description": "Provides current weather information",
  "url": "https://weather-agent.example.com",
  "version": "1.0.0",
  "authentication": {
    "schemes": ["OAuth2"]
  },
  "defaultInputModes": ["text/plain"],
  "defaultOutputModes": ["application/json"],
  "capabilities": {
    "streaming": false,
    "pushNotifications": true
  },
  "skills": [
    {
      "id": "get-weather",
      "name": "Weather Forecast",
      "description": "Retrieves weather data for a given location",
      "tags": ["weather", "forecast"],
      "examples": ["Get weather for New York", "Forecast for London"]
    }
  ]
}

---

If an LLM model is a destilled version of all text. all use  of it is a way to narrow the scope for its search or associciation 

---

<!-- .slide: data-fullscreen-->

<div class="tweet"  data-src="https://x.com/scaling01/status/1911844152578355317"></div>

---

![](./diagrams/multi_agent.svg)