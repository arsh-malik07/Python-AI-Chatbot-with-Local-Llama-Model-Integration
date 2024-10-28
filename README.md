# Python-AI-Chatbot-with-Local-Llama-Model-Integration

A conversational AI chatbot built using Ollama and LangChain that maintains conversation context and runs completely locally on your machine.

## Features

- Local execution using Ollama's LLama 3.1 model
- Maintains conversation history for contextual responses
- Simple command-line interface
- Memory-enabled responses that can reference previous parts of the conversation
- Easy exit command ("bye llama")

## Prerequisites

Before running this chatbot, make sure you have:

1. Python 3.10 or higher installed
2. Ollama installed and running on your machine
3. LLama 3.1 model pulled in Ollama

## Installation

1. First, install Ollama by following instructions at [Ollama's website](https://ollama.ai)

2. Pull the LLama 3.1 model:
```bash
ollama pull llama3.1
```

3. Install the required Python packages:
```bash
pip install langchain-ollama langchain-core
```

## Usage

1. Start the Ollama server:
```bash
ollama serve
```

2. In a new terminal window, run the chatbot:
```bash
python chatbot.py
```

3. Start chatting with the bot! The bot will remember your conversation history and provide contextual responses.

4. To exit the chat, simply type: `bye llama`

## How It Works

The chatbot uses several key components:

- `OllamaLLM`: Connects to your local Ollama instance
- `ChatPromptTemplate`: Structures the conversation with context
- Conversation memory: Maintains the chat history in the `context` variable
- Command loop: Continuously processes user input until exit command

## Example Conversation

```
Welcome to this AI Chatbot! Type 'bye llama' to quit
You: What is your favorite color?
Bot: I don't actually have favorite colors since I'm an AI language model. I can discuss colors and their properties, but I don't experience personal preferences or emotions like humans do.
You: Remember that answer for later
Bot: I understand you want me to remember my previous response about not having favorite colors. I've stored this in our conversation context and will remember that I explained I'm an AI that doesn't have personal preferences like favorite colors.
You: What did you say earlier about colors?
Bot: Earlier, I explained that I don't have favorite colors because I'm an AI language model. I mentioned that while I can discuss colors and their properties, I don't experience personal preferences or emotions like humans do.
```

## Customization

You can modify the `template` variable in the code to change how the bot processes context and questions. The current template includes:
- Conversation history (`{context}`)
- Current question (`{question}`)

## Troubleshooting

If you encounter issues:

1. Ensure Ollama is running (`ollama serve`)
2. Verify LLama 3.1 is installed (`ollama list`)
3. Check your Python environment and required packages
4. Ensure you're not running in WSL if Ollama is installed in Windows (or vice versa)

## License

This project is released under the MIT License.
