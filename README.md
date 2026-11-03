# OpenAI Demo: Chat and Completion APIs

> A practical Google Colab notebook for learning how to call OpenAI models with Python.

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Run%20in-Google%20Colab-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![OpenAI](https://img.shields.io/badge/API-OpenAI-412991?logo=openai&logoColor=white)](https://platform.openai.com/)

## Overview

This project demonstrates how to use the OpenAI Python client from a Google Colab notebook. It is designed as a hands-on reference for understanding the difference between:

- **Chat Completions** — conversation-oriented requests using system and user messages.
- **Text Completions** — prompt-based text generation.

The examples use the legacy `openai==0.28` client interface and the `gpt-3.5-turbo` and `babbage-002` models shown in the notebook.

## Features

- 🔐 Secure API-key loading through Google Colab Secrets
- 📋 Listing available OpenAI models
- 💬 Single-turn and multi-turn chat conversations
- 🎛️ Controlling `max_tokens` and `temperature`
- 🔁 Generating multiple responses with `n`
- 😊 Sentiment analysis
- 🌍 Translation to Hindi
- 🗣️ Language detection
- 👨‍💻 AI-assisted Python code generation
- 📝 Text completion from a single prompt

## Project Structure

```text
Open_AI_Demo/
├── OpenAI_Demo_Chat_Competion_API.ipynb
└── README.md
```

## Getting Started

### Option 1: Run in Google Colab

1. Open [`OpenAI_Demo_Chat_Competion_API.ipynb`](./OpenAI_Demo_Chat_Competion_API.ipynb) in Google Colab.
2. Create an OpenAI API key in the [OpenAI Platform](https://platform.openai.com/api-keys).
3. In Colab, open **Secrets** from the left sidebar.
4. Add the key using the secret name expected by the notebook: `ΟΡΕΝΑΙ_API_KEY`.
5. Enable notebook access to the secret.
6. Run the cells from top to bottom.

> **Security:** Never paste an API key directly into a notebook, commit it to source control, or share it in screenshots. If you rename the secret to the conventional `OPENAI_API_KEY`, update the first notebook cell accordingly.

### Option 2: Run locally

Create a virtual environment and install the dependency used by the notebook:

```bash
python -m venv .venv
```

Activate it:

```bash
# Windows PowerShell
.venv\Scripts\Activate.ps1

# macOS/Linux
source .venv/bin/activate
```

Install the pinned client:

```bash
pip install openai==0.28
```

Then open the notebook with Jupyter:

```bash
pip install notebook
jupyter notebook
```

> The notebook is written for the pre-1.0 OpenAI Python client. For new applications, consult the [current OpenAI Python documentation](https://github.com/openai/openai-python) before upgrading, because the client interface has changed.

## Example

The notebook initializes the legacy client and sends a chat request like this:

```python
import openai

openai.api_key = OPENAI_API_KEY

response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "What is Python?"}
    ],
)

print(response["choices"][0]["message"]["content"])
```

## Notebook Flow

1. Load the API key from Colab Secrets.
2. Install and import `openai==0.28`.
3. Configure the OpenAI client.
4. Query the available models.
5. Run ChatCompletion examples with different parameters.
6. Compare ChatCompletion and Completion behavior.

## Important Notes

- API calls may incur usage charges according to your OpenAI account and selected model.
- Model availability, pricing, and limits can change over time.
- Do not send sensitive, private, or regulated data in prompts.
- The notebook contains example outputs captured from a previous run; they may differ when executed again.
- The filename contains `Competion`; this is the existing notebook filename and does not affect execution.

## Troubleshooting

| Issue | Suggested fix |
|---|---|
| Authentication error | Confirm the Colab Secret name, access permission, and API-key validity. |
| Model unavailable | Check the model name and current model availability in the OpenAI Platform. |
| Package/API errors | Confirm that `openai==0.28` is installed, or migrate the notebook to the current client API. |
| Empty or unexpected output | Inspect the full response object and verify the selected model and prompt. |

## References

- [OpenAI Platform](https://platform.openai.com/)
- [OpenAI Python library](https://github.com/openai/openai-python)
- [Google Colab](https://colab.research.google.com/)

## License

No license has been specified for this project.
