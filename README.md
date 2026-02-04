# Agent-Driven Research & Critique System

An autonomous research agent built with **LangGraph** and **Google Gemini**. This system doesn't just search; it iteratively researches a topic, drafts a summary, critiques its own work, and performs additional research to fill gaps until it meets a quality threshold.

## 🤖 How It Works

The project implements a stateful directed acyclic graph (DAG) where each node represents a specific stage of the research process:

1.  **`query_gen`**: Generates three targeted search queries based on the initial topic.
2.  **`researcher`**: Uses the **Tavily API** to fetch real-time web context for the queries.
3.  **`writer`**: Synthesizes the gathered context into a concise summary.
4.  **`reviewer`**: Critiques the summary for inaccuracies, missing strategic elements, or depth.
5.  **`should_continue`**: A conditional logic gate that decides whether to loop back for more research or finish based on the critique or iteration count.

## 🛠️ Technical Stack

* **Orchestration:** [LangGraph](https://github.com/langchain-ai/langgraph)
* **LLM:** [Google Gemini 2.0 Flash](https://blog.google/technology/ai/google-gemini-ai/)
* **Search Engine:** [Tavily AI](https://tavily.com/)
* **Language:** Python 3.11+

## 📂 Code Highlights

### The Agent State
