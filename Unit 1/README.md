# 🤖 Local AI Agent From Scratch (Python & Qwen)

A lightweight, local AI agent built from scratch in Python as part of the Hugging Face AI Agents course. This project runs entirely offline on a local PC using **Qwen 2.5** via **Ollama**, allowing for secure, cost-free agentic workflows and tool-calling experimentation.

---

## 🚀 What I Built & Learned
Through this exercise, I moved beyond standard chatbot prompts to build an autonomous agentic loop. Key takeaways include:
* **The Agent Architecture:** Building a custom Python `Agent` class that manages conversation history, system prompts, and execution loops.
* **The ReAct Loop:** Understanding how models alternate between reasoning, acting (calling tools), and observing outputs.
* **Tool Integration:** Defining custom JSON schemas, passing them to the model, and intercepting tool calls to execute local Python functions.
* **Local LLM Execution:** Leveraging lightweight open-source models (`qwen2.5:3b`) locally via Ollama to handle structured function calling without relying on cloud APIs.

---

## 🔄 Core Concept: The Thought-Action-Observation Cycle
Agents operate on a continuous loop rather than a single-turn prompt response:
1. **Thought (Reasoning):** The LLM analyzes the user's request and plans the next step.
2. **Action (Execution):** The agent takes action by triggering a tool with assigned arguments (e.g., calling `get_weather(city="Singapore")`).
3. **Observation (Feedback):** The tool returns data, an error message, or system logs, which are fed back into the agent's memory to guide the next thought or final answer.

---

## 🧠 Key Concepts Explored: Chain of Thought (CoT) vs. ReAct
* **Chain of Thought (CoT):** A prompting technique guiding a model to think step-by-step internally. Best suited for internal logic, math, and reasoning tasks **without external tools**.
* **ReAct (Reasoning + Acting):** Extends CoT by interleaving internal reasoning steps with external actions (tool usage). Best suited for info-seeking and dynamic multi-step tasks.

* In this segment, I built a dummy agent that is pretty primitive, it uses no frameworks so everything is done manually. Writting the functions was the tuffest part, but I still have more to learn, this was just a basic foundation.

Next up: Types of Agent Actions(Using frameworks this time)
* **JSON Agent:** The action and inputs are specified in a strict JSON format that a program parses.
* **Function-Calling Agent:** A refined version where the model is fine-tuned to natively output structured tool calls mapped to local APIs (used in this project).
* **Code Agent:** The agent writes an executable code block (e.g., Python code) that is executed in an external interpreter, offering high flexibility and expressiveness.

---
## 💻 Tech Stack
* Python (Core logic & Agent class)
* Ollama (Local model runtime server)
* Qwen 2.5 (3B) (Local LLM supporting native tool calling)
* Hugging Face Hub / OpenAI Client SDK (API communication layer)
