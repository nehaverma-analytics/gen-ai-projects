# 🧠 AI Book Summarizer and Answer Evaluator

This project presents an AI-based **Book Summarizer and Answer Evaluator**, designed to provide a summary of a book or any pdf document and lets the user ask questions about the bok/document. It also has an 'Evaluator' LLM which validates the answer given by the summarizer LLM.

## Projects

- [Book Summrizer and Evaluator using OpenAI and Google frontier models](./book-summarizer-and-evaluator.ipynb)

---

## 📌 Project Objective

To demonstrate how a language model (LLM) can be used to:
- Summarize a book.
- Respond to user queries on the summary eg. stotyline, key take-aways etc..
- Simulate a conversational book expert.
- Evaluate the accuracy of the Summarizer LLM.
- Have an interactive chat session on the Gradio UI.

## 🛠️ Tech Stack

- **Python 3.11+**
- **OpenAI API** – for summarizer model inference
- **Google API** - for evaluation model
- **Environment Variables (.env)** – to securely manage API keys
- **Gradio** - UI for interactive chat

---

## 🚀 Features

- Modular prompt template creation
- Accepts dynamic user input
- Demonstrates conversational response from OpenAI's LLM
- Demonstrates validation response from Google API 
- Creates instant User Interface using Gradio

---

## 🔐 Setup Instructions

1. **Install dependencies**
   ```bash
   pip install openai python-dotenv

2. **Set your OpenAI API key** 
   Create a .env file:  
   OPENAI_API_KEY=your-api-key-here
   GOOGLE_API=your-api-key-here

3. **Run the notebook**
Launch Jupyter Notebook and open book-summarizer-and-evaluator.ipynb

---

## 📈 Future Enhancements
* Add RAG for more specific context for conversations
* Deploy as a Flask or Streamlit web app

---

## 🤝 Contributions
Feel free to fork this repo, add enhancements, and submit a pull request!

---

## ✨ Author
Developed by Neha Verma

Visit 🔗 [LinkedIn](https://www.linkedin.com/in/nehavermadataanalytics).

