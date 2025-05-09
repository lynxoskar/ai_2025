//Chief Technology Officer of Palantir
https://www.youtube.com/watch?v=DTG393KqOGc 
//Sridhar Ramaswamy, CEO of Snowflake - about not building llms 
https://youtu.be/qF2PsdSxlXI?si=2O7cSAmxzBeegAEL
//claude code
https://www.anthropic.com/engineering/claude-code-best-practices
//STANFORD 2024 REPORT
https://hai.stanford.edu/ai-index/2024-ai-index-report
//clickhouse mcp db agent
https://clickhouse.com/blog/agenthouse-demo-clickhouse-llm-mcp?utm_content=buffere886a&utm_medium=social&utm_source=twitter&utm_campaign=buffer
//agents
https://x.com/i/status/1907412051787657516


im doing a presentation on ai for my company. this is my inital plan 

start - 

1. Timeline with pivotal moments of ai from the start with deepseek and to current day
    - enumerate llms at last presentation 2years ago. 
    - enumerate todays offering of fronteir LLM models and products. normal up till max 200$ offerings
    

2. Enablers - making the ai happen.  

    """“The beaver told the rabbit as they stared at the Hoover Dam: No, I didn’t build it myself, but it’s based on an idea of mine.”
    — Charles Hard Townes"""  

    reasoning of what made this happen, big corpus of data/text. hardware and compute comming online. 
    Making a referece to guns germs and steels example of textprinting need reading consumers to be any revolution.... //look up citation
    enablers and the ability to adopt is key. Yesterdays success is the most dangerous thing you face...

3.  Current uptake and monies spend on ai by companies. Lesson learnt from them. 
    look into 7 misstakes podcast
    ""The future is allready here, its ""look into Adrej Karpathys post about ai being the equalizer. 

link 

https://x.com/scaling01/status/1911844152578355317 

4.  Revisit an old ai talk - an llm is still only a next token machine.
    - explain temperature, k - p configuration. Help files and flows that have been discovered making the job easier for the llm. Describing what manual steps one can do make the llm useage better. 
    - Using the llm to write the instructions in iterations. walk into agents.. just a bunch of python code and api key...
    ###
    At their core, LLMs operate as prediction engines that take sequential text as input and predict the next token based on the data they were trained on. This process is repeated, adding the predicted token to the sequence to predict the subsequent one. The prediction of the next token is based on the relationships learned from the vast amounts of text in the LLM's training data. - compression?
    -
    Prompt engineering is the process of designing high-quality prompts that guide LLMs to produce accurate outputs. When you write a prompt, you are essentially trying to set up the LLM to predict the desired sequence of tokens that constitutes your answer or output. Effective prompt engineering involves understanding how the model works and then tinkering with various aspects of the prompt, such as word choice, style, tone, structure, and the context provided, to achieve the desired outcome
    General prompting/zero-shot prompting: This involves providing a task description without any examples. The LLM relies solely on its pre-existing knowledge to generate a response.
    •
    ###
    One-shot and few-shot prompting: These techniques provide the LLM with one or a few examples to demonstrate the desired output format or pattern. This helps the model understand the task better and can steer it towards a specific type of response.
    •
    ###
    System, contextual, and role prompting: These techniques allow you to set the overall context and purpose (system prompt), provide specific background information (contextual prompt), or assign a specific character or identity to the LLM (role prompt). This can influence the style, tone, and focus of the LLM's output.
    •
    ###
    Chain of Thought (CoT) prompting: This technique encourages the LLM to generate intermediate reasoning steps before arriving at the final answer. By explicitly asking the model to "think step by step," you can improve its performance on complex tasks that require reasoning.
    •
    ###
    ReAct (reason & act) prompting: This paradigm enables LLMs to solve complex tasks by combining natural language reasoning with the use of external tools. The LLM reasons about the problem, plans an action, uses a tool (like a search engine or code interpreter), observes the result, and then updates its reasoning to take further action. This thought-action loop is a fundamental step towards agent modeling as it allows the LLM to interact with the environment to gather information and achieve goals.

    ###
    example aider claude code - open ai codex
    Claude Code facilitates automation through features like:
    •
    Customizable setup using CLAUDE.md files: These special files allow you to provide Claude with persistent context, such as common bash commands, core files, code style guidelines, and testing instructions. Claude automatically pulls this information into prompts, optimizing context gathering. You can instruct Claude to automatically incorporate information into these files using the # key.
    •
    Curating allowed tools: For safety, Claude Code requests permission for actions that might modify your system by default. You can customize an allowlist to permit additional tools that you deem safe.
    •
    Access to the shell environment and external tools: Claude can leverage convenience scripts, functions, and more complex tools through MCP and REST APIs.
    •
    Custom slash commands: You can store prompt templates in Markdown files within the .claude/commands folder, making them available as slash commands for repeated workflows.
    •
    Headless mode: Claude Code includes a headless mode (claude -p) for non-interactive contexts like CI, pre-commit hooks, build scripts, and automation. This allows for programmatic integration of Claude into larger workflows. Headless mode can be used for tasks like issue triage triggered by GitHub events.

    ### 
    look at agents in agentic patterns

    ### andrejs take on the new api is text
    https://x.com/karpathy/status/1914494203696177444





6.  Revisitin the initial citation, is it faster horses we are after? What does this mean for lynx -> data - apis as text.   Process vs Outcome driven development. Time spend exploring and using tools. Less people working or better and more positive outcomes?

