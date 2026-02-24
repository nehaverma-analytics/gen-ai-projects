# LLM Judging Content From Other LLMs

## Overview

This notebook:

1.  Loads API keys using dotenv.
2.  Uses OpenAI to generate a challenging evaluation question.
3.  Sends the same question to multiple LLMs.
4.  Collects their responses.
5.  Uses another OpenAI model to judge and rank the responses.
6.  Prints the ranked order of competitors.

## Environment Setup

The notebook expects the following environment variables:

-   OPENAI_API_KEY
-   ANTHROPIC_API_KEY
-   GOOGLE_API_KEY
-   DEEPSEEK_API_KEY
-   GROQ_API_KEY

It uses `load_dotenv(override=True)` to load them.

## 🛠️ Tech Stack

- **Python 3.11+**
- **OpenAI API** – for language model inference
- **Environment Variables (.env)** – to securely manage API keys

## Question Generation

A request is sent to:

-   Model: `gpt-4o-mini`

Prompt:

"Please come up with a challenging, nuanced question that I can ask a
number of LLMs to evaluate their intelligence. Answer only with the
question, no explanation."

The generated question is stored and printed.

## Competitor Models

The generated question is sent to the following models:

1.  `gpt-4o-mini` (OpenAI)
2.  `claude-3-7-sonnet-latest` (Anthropic)
3.  `gemini-2.0-flash` (Google via OpenAI-compatible endpoint)
4.  `deepseek-chat` (DeepSeek via OpenAI-compatible endpoint)
5.  `llama-3.3-70b-versatile` (Groq via OpenAI-compatible endpoint)
6.  `llama3.2` (Ollama local model)

Each response is:

-   Displayed using Markdown
-   Stored in a list of answers
-   Associated with its model name in a competitors list

Ollama model is pulled using:

`!ollama pull llama3.2`

## Aggregation

All responses are concatenated into a single formatted string:

-   "Response from competitor X"
-   Followed by the model's answer

## Judging

A judging prompt is constructed that:

-   Specifies the number of competitors
-   Includes the original question
-   Includes all responses
-   Instructs the judge to rank responses by clarity and strength of
    argument
-   Requires JSON-only output in the format:

{"results": \["best", "second", "third", ...\]}

The judging model used:

-   `o3-mini` (OpenAI)

The JSON response is parsed using `json.loads`.

## Ranking Output

The ranked competitor numbers are mapped back to model names.

Final output prints:

Rank: 1: `<model_name>`{=html} Rank: 2: `<model_name>`{=html} ...

## Key Concepts Demonstrated

- Multi-model orchestration
- API abstraction via OpenAI-compatible interfaces
- Cross-model evaluation
- Prompt engineering for structured outputs
- JSON-based ranking system
- Automated benchmarking framework

## Potential Extensions

- Add scoring (not just ranking)
- Add evaluation dimensions (logic, creativity, factuality, tone)
- Store results in a database
- Run multiple trials and compute averages
- Visualize rankings
- Add bias detection analysis
- Build a Streamlit dashboard
- Automate benchmarking across different question categories

## Author
Developed by Neha Verma

Visit 🔗 [LinkedIn](https://www.linkedin.com/in/nehavermadataanalytics).
