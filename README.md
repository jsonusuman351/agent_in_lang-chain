# 🤖 Building  AI Agent with LangChain

![LangChain](https://img.shields.io/badge/LangChain-0086CB?style=for-the-badge&logo=langchain) ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai) ![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python)

Hey there! Welcome to my latest adventure in the world of AI: building an **autonomous agent**. After learning about chains and tool calling, I wanted to take the next logical step and create an AI that can think for itself, make decisions, and use tools to accomplish a goal.

This repository, documented in a single Jupyter Notebook, is my journey of building a simple but powerful agent that can use the DuckDuckGo search engine to answer questions about recent events—something a regular LLM can't do on its own!

---

### 🤔 The "Why" Behind AI Agents

I realized that while chains and tool-calling are powerful, they follow a pre-defined path. An **agent**, on the other hand, is different. It uses an LLM not just to answer questions, but to *reason* about what steps it needs to take.

An agent operates in a loop:
1.  **Thought**: It thinks about the user's request and decides if it needs a tool.
2.  **Action**: It chooses a tool and decides what input to give it.
3.  **Observation**: It looks at the tool's output.
4.  **Repeat**: Based on the observation, it decides what to do next—maybe use another tool, or formulate the final answer.

This reasoning loop, often called the **ReAct framework (Reason + Act)**, is what gives agents their autonomy.

---

### ✨ Core Concepts I've Implemented

This project is a step-by-step guide to building a basic LangChain agent from scratch:

1.  **Defining Tools**:
    -   An agent is only as good as its tools. For this project, I gave the agent a single, powerful tool: `DuckDuckGoSearchRun`. This allows the agent to browse the internet to find up-to-date information.

2.  **Creating the Agent Prompt**:
    -   This was a crucial step. The prompt is like the agent's "operating system." I used LangChain's `hub.pull("hwchase17/react")` to get a standardized ReAct prompt template. This special prompt instructs the LLM on how to think, how to format its thoughts, and how to use the available tools.

3.  **Initializing the Agent**:
    -   I used the `create_react_agent` function to bring everything together: the **LLM** (the "brain"), the **tools** (the "hands"), and the **prompt** (the "instructions"). This function creates the core reasoning engine of the agent.

4.  **Setting Up the Agent Executor**:
    -   The `AgentExecutor` is the runtime that actually makes the agent work. It's the component that takes the agent's decisions, runs the chosen tools, gets the results, and feeds them back to the agent in a continuous loop until the task is complete.

5.  **Running and Observing**:
    -   Finally, I invoked the agent with a question it couldn't possibly know the answer to on its own ("Who won the last cricket world cup?"). It was amazing to see the agent's thought process in real-time as it decided to use the search tool, found the answer, and then formulated a perfect response.

---

### 🛠️ Tech Stack

-   **Core AI Framework**: LangChain
-   **LLM Provider**: OpenAI
-   **Tools**: DuckDuckGo Search
-   **Notebook Environment**: Jupyter
-   **Core Libraries**: `langchain`, `langchain-openai`, `langchainhub`, `duckduckgo-search`

---

### ⚙️ Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/jsonusuman351/agent_in_lang-chain.git](https://github.com/jsonusuman351/agent_in_lang-chain.git)
    cd agent_in_lang-chain
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    # It is recommended to use Python 3.10 or higher
    python -m venv venv
    .\venv\Scripts\activate
    ```

3.  **Install the required packages:**
    Since I worked directly in a Jupyter Notebook, there isn't a `requirements.txt` file. You can install all the necessary libraries by running this command:
    ```bash
    pip install langchain langchain-openai langchainhub duckduckgo-search python-dotenv jupyter
    ```

4.  **Set Up Your OpenAI API Key:**
    -   To run the notebook, you'll need to provide your OpenAI API key. I recommend setting it as an environment variable, but for a quick start, you can also place it directly in the notebook (just remember not to commit it to GitHub!).

---

### 🚀 How to Use This Project

The entire workflow is contained within a single, well-documented Jupyter Notebook.

1.  **Launch Jupyter:**
    Make sure your virtual environment is active, then run:
    ```bash
    jupyter notebook
    ```
2.  **Open the Notebook:**
    In the Jupyter interface that opens in your browser, click on `agent_in_lang-chain.ipynb`.
3.  **Add Your API Key:**
    Ensure your OpenAI API key is accessible within the notebook.
4.  **Run the Cells:**
    You can run each cell in the notebook sequentially to see the entire process, from setting up the tools to watching the agent think and act.

---

### 🔬 A Tour of My First Agent

I've organized this entire project into a single Jupyter Notebook to make it easy to follow my journey of building an autonomous AI.

<details>
<summary>Click to view the code layout</summary>

```
agent_in_lang-chain/
│
└── agent_in_lang-chain.ipynb    # The complete end-to-end workflow is in this single notebook
```
</details>

---

---
