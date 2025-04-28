# 5 Most Popular Agentic AI Design Patterns

This document summarizes the five key agentic AI design patterns outlined in a thread by Akshay 🚀 (@akshay_pachaar) on X, posted on April 2, 2025. These patterns illustrate how AI agents, powered by Large Language Models (LLMs), can perform complex tasks autonomously by mimicking human-like problem-solving and collaboration. The diagrams below are rendered using Mermaid syntax.

---

## 1. Reflection Pattern

### Overview
The Reflection Pattern enables an AI to review and refine its own output iteratively. The LLM generates an initial response, critiques it for errors or gaps, and then improves it through multiple iterations. This self-critique process enhances the quality of outputs in tasks like coding, writing, or answering questions.

### Key Feature
- Self-evaluation and iteration for polished results.

### Diagram
```mermaid
flowchart TD
    A[User] -->|Query| B[LLM<br>Generate]
    B --> C[Initial Output]
    C --> D[LLM<br>Reflect]
    D -->|Iterate| C
    D --> E[Reflected Output]
    E --> A


2. Tool Use Pattern
Overview
In the Tool Use Pattern, the LLM acts as the "brain" and uses external tools as its "hands" to perform actions. These tools can include querying a vector database, calling APIs, or executing Python scripts, allowing the AI to go beyond its internal knowledge.
Key Feature
Extends LLM capabilities through external tool integration.

Diagram (Mermaid)
mermaid

flowchart TD
    A[User] -->|Query| B[LLM<br>Generate]
    B -->|Tool calling| C[Tools & APIs<br>Vector Database, APIs]
    C --> B
    B --> D[Response]
    D --> A

ReAct Pattern (Reasoning and Acting)
Overview
The ReAct Pattern combines Reflection and Tool Use. The AI reasons about its generated output, uses tools to interact with the external environment, and reflects on the results. This iterative process of reasoning and acting makes it a powerful approach for dynamic problem-solving.
Key Feature
Combines self-reflection with external tool interaction.

Diagram (Mermaid)
mermaid

flowchart TD
    A[User] -->|Query| B[LLM<br>Reason]
    B -->|Action| C[Tools]
    C --> D[Environment]
    D -->|Result| B
    B --> E[LLM<br>Generate]
    E --> F[Response]
    F --> A
    G[Agent] --> B

4. Planning Pattern
Overview
The Planning Pattern focuses on breaking down complex tasks into smaller subtasks. The AI creates a roadmap by subdividing tasks and outlining objectives, executing each step methodically. It often leverages the ReAct pattern for individual subtasks.
Key Feature
Task decomposition and strategic execution.

Diagram (Mermaid)
mermaid

flowchart TD
    A[User] -->|Query| B[Planner]
    B --> C[Generated Tasks]
    C --> D[ReAct Agent]
    D -->|Execute single task| C
    D --> E{Finished?}
    E -->|NO| C
    E -->|YES| F[Response]
    F --> A

5. Multi-Agent Pattern
Overview
The Multi-Agent Pattern involves multiple specialized AI agents working together, each with a distinct role. For example, in a software development scenario, agents might include a Product Manager (PM), Tech Lead, Developer, and DevOps Engineer, collaborating to deliver a unified product.
Key Feature
Collaborative teamwork among specialized agents.

Diagram (Mermaid)
mermaid

flowchart TD
    A[User] -->|Query| B[PM Agent]
    B -->|Delegation| C[Tech Lead Agent]
    B -->|Delegation| D[DevOps Agent]
    B -->|Delegation| E[SDE Agent]
    C --> F[Collaboration]
    D --> F
    E --> F
    F --> G[Response]
    G --> A

