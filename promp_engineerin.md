---
customTheme: custom-cyberpunk
show
---


Based on your request, I’ve reviewed the document "Prompt Engineering_v7.pdf" and identified the key prompt engineering techniques described within it. Below, I provide a summary of each technique followed by a Mermaid flowchart illustrating its structure or process. I assume your phrase "mermaid diagram of if" was intended to mean "a Mermaid diagram for each technique," given the plural "techniques" in your query. Thus, I’ve created a separate Mermaid diagram for each technique listed in the document’s prompting techniques section (pages 13–42). These diagrams are provided as code that you can copy into a Mermaid-compatible viewer (e.g., Mermaid Live Editor) to visualize the flowcharts, as they may not render directly in this text format.

---

### Summary of Prompt Engineering Techniques with Mermaid Diagrams

The document "Prompt Engineering_v7.pdf" explores various techniques for crafting effective prompts to guide large language models (LLMs) in generating accurate and relevant outputs. Below is a summary of each technique, accompanied by a Mermaid flowchart to illustrate its structure or flow.

---

1. **General Prompting / Zero Shot**  
   **Summary:** This is the simplest prompting method, where a task description and initial text are provided without any examples. The LLM relies solely on its pre-trained knowledge to produce an output, making it a "zero-shot" approach.  
   
   ![](./diagrams/context_prompt.svg)

   ```
   ``` what is this```
   
---

--

2. **One-Shot & Few-Shot Prompting**  
   **Summary:** These techniques involve including one example (one-shot) or multiple examples (few-shot) in the prompt to demonstrate the desired output pattern or format, helping the LLM understand the task more effectively.  

   **Mermaid Diagram:**
   ```mermaid
   graph LR
   A[Prompt with Examples] --> B[Output]
   ```

3. **System Prompting**  
   **Summary:** This technique defines the overarching context or purpose for the LLM, such as specifying the task (e.g., classification, translation) or output format (e.g., JSON), guiding the model’s behavior at a high level.  
   **Mermaid Diagram:**
   ```mermaid
   graph LR
   A[System Instruction] --> B[Task Prompt] --> C[Output]
   ```

---

4. **Contextual Prompting**  
   **Summary:** Provides specific background details or task-relevant information to the prompt, enabling the LLM to tailor its response more accurately to the given scenario.  
   **Mermaid Diagram:**
   ```mermaid
   graph LR
   A[Context] --> B[Task Prompt] --> C[Output]
   ```

5. **Role Prompting**  
   **Summary:** Assigns a specific role or persona to the LLM (e.g., travel guide, teacher), directing it to generate responses consistent with that role’s perspective, tone, or expertise.  
   **Mermaid Diagram:**
   ```mermaid
   graph LR
   A[Role Assignment] --> B[Task Prompt] --> C[Output]
   ```

6. **Step-Back Prompting**  
   **Summary:** The LLM is first prompted with a general question related to the task to activate broader knowledge, then the answer is used in a subsequent prompt to address the specific task, enhancing reasoning and accuracy.  
   **Mermaid Diagram:**
   ```mermaid
   graph LR
   A[General Question] --> B[Answer to General Question] --> C[Specific Task Prompt] --> D[Output]
   ```

7. **Chain of Thought (CoT)**  
   **Summary:** Encourages the LLM to produce intermediate reasoning steps before delivering the final answer, improving performance on complex tasks by making the thought process explicit.  
   **Mermaid Diagram:**
   ```mermaid
   graph LR
   A[Prompt] --> B[Reasoning Step 1] --> C[Reasoning Step 2] --> D[Final Answer]
   ```

8. **Self-Consistency**  
   **Summary:** The LLM generates multiple responses to the same prompt using varied reasoning paths (often with higher temperature settings), then selects the most consistent answer to improve reliability.  
   **Mermaid Diagram:**
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

9. **Tree of Thoughts (ToT)**  
   **Summary:** Explores multiple reasoning paths or ideas in a branching structure, allowing the LLM to consider various possibilities before converging on a final output, useful for deliberate problem-solving.  
   **Mermaid Diagram:**
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

10. **ReAct (Reason & Act)**  
    **Summary:** Combines reasoning and action, where the LLM first reasons about the task and then performs an action (e.g., generating text or code) based on that reasoning, synergizing thought and execution.  
    **Mermaid Diagram:**
    ```mermaid
    graph LR
    A[Prompt] --> B[Reasoning] --> C[Action] --> D[Output]
    ```

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

12. **Code Prompting**  
    **Summary:** Utilizes prompts to perform code-related tasks, such as writing, explaining, translating, or debugging code, leveraging the LLM’s ability to handle programming languages.  
    **Mermaid Diagram:**
    ```mermaid
    graph LR
    A[Prompt for Code Task] --> B[Perform Code Task] --> C[Output]
    ```

