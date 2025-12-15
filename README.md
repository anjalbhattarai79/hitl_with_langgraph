# 🤖 HITL with LangGraph: Human-in-the-Loop Demo 🚀

## What is Human-in-the-Loop (HITL)? 🤔
Human-in-the-Loop (HITL) is a powerful AI paradigm where humans actively participate in the decision-making process of an automated system. Instead of letting AI run fully autonomously, HITL allows for **human oversight, approval, or intervention** at key points. This ensures safety, accuracy, and ethical control, especially in sensitive applications like content moderation, medical diagnostics, or conversational AI. Think of it as a safety net: the AI proposes actions, but a human gives the final thumbs up (or down)! 👍👎

## Implementation in This Dummy Project 🛠️
This is a simple dummy project demonstrating HITL using **LangGraph** (a framework for building stateful, graph-based AI workflows) and **Google's Gemini LLM**. The goal is to show how to interrupt an AI conversation for human approval before responding to user queries.

### Key Features:
- **State Management**: Uses a `ChatState` with messages to track conversation history.
- **Interruption Logic**: The `chat_node` function interrupts the flow with an approval prompt when the AI is about to answer a question. It asks: "Approve this question? yes/no" 📝
- **Human Input**: If approved, the LLM generates a response; if not, it returns a rejection message. The graph resumes based on user input via `Command(resume)`.
- **Persistence**: Employs `MemorySaver` for checkpointing, allowing the graph to pause and resume across sessions.


### How It Works (Step-by-Step):
1. **Setup**: Load environment variables, initialize the Gemini LLM, and define the chat state.
2. **Graph Building**: Create a simple graph with one node (`chat`) that handles the HITL logic.
3. **Execution**: Invoke the graph with a user message (e.g., "Explain gradient descent in a simple way.").
4. **Interruption**: The graph pauses, displaying an interrupt message for human approval.
5. **Resume**: Based on user input (yes/no), the graph either proceeds to generate an AI response or rejects it.
6. **Output**: Prints the final result, including messages and any interrupt data.

### Running the Project:
- Ensure you have a `.env` file with your Google API key.
- Run the `main.ipynb` notebook cell by cell.
- When prompted for approval, enter "yes" or "no" in the input field.
- This is a dummy setup—expand it for real-world use cases! 🔧

### Dependencies:
- `langchain-google-genai`
- `langgraph`
- `python-dotenv`
- Jupyter Notebook for execution.

Feel free to fork, modify, and experiment! If you have questions, open an issue. 🌟
