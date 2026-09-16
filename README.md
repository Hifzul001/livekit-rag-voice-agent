# LiveKit RAG Voice Agent

A real-time conversational AI voice assistant built using **LiveKit**, **LangChain**, and **FAISS**, powered by Retrieval-Augmented Generation (RAG). The agent enables natural voice conversations, retrieves relevant information from custom documents, and delivers low-latency, context-aware responses through an end-to-end speech pipeline.

## Features

- **Real-Time Voice Conversations** using LiveKit's low-latency communication framework.
- **Retrieval-Augmented Generation (RAG)** for accurate, source-grounded responses from PDF knowledge bases.
- **Semantic Vector Search** with FAISS for fast local document retrieval.
- **Speech-to-Text → LLM → Text-to-Speech** pipeline for seamless conversational interaction.
- **Custom Knowledge Base** with easy ingestion of domain-specific documents.
- **Modular Architecture** supporting interchangeable prompts and retrieval components.

## Tech Stack

- **Language:** Python
- **Voice:** LiveKit
- **LLM Framework:** LangChain
- **Vector Database:** FAISS
- **Speech Services:** Deepgram, Cartesia
- **LLM:** OpenAI GPT Models

## Project Structure

```text
livekit-rag-voice-agent/
│
├── src/                 # Voice agent & RAG pipeline
├── data/                # PDF knowledge base
├── chat_bot.py          # Conversational agent
├── voice_lang.py        # LiveKit voice entry point
├── requirements.txt
├── .env.example
└── README.md
```

## Installation

1. Clone the repository

```bash
git clone https://github.com/Hifzul001/livekit-rag-voice-agent.git
cd livekit-rag-voice-agent
```

2. Create a virtual environment

```bash
python -m venv venv
```

**Windows**

```bash
venv\Scripts\activate
```

**Linux / macOS**

```bash
source venv/bin/activate
```

3. Install dependencies

```bash
pip install -r requirements.txt
```

4. Configure environment variables

Create a `.env` file in the root directory.

```env
LIVEKIT_API_KEY=
LIVEKIT_API_SECRET=
LIVEKIT_URL=

OPENAI_API_KEY=
DEEPGRAM_API_KEY=
CARTESIA_API_KEY=
```

## Run the Voice Agent

```bash
python voice_lang.py
```

The agent connects to your LiveKit room and starts accepting real-time voice interactions.

## How It Works

1. User speaks into a LiveKit room.
2. Deepgram converts speech to text.
3. LangChain retrieves relevant document chunks from FAISS.
4. OpenAI generates a context-aware response.
5. Cartesia converts the response back to natural speech.
6. The spoken answer is streamed back to the user.

## Future Improvements

- Conversation memory across sessions
- Multi-document indexing
- Streaming response optimization
- Support for Pinecone and cloud vector stores

## License

This project is licensed under the MIT License.
