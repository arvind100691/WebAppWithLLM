# WebAppWithLLM
A web-based chat interface for interacting with LLMs via LM Studio, featuring persistent chat history, markdown formatting, and secure API proxying.

## Features
- **Chat Interface**: Clean, readable UI with user/assistant message bubbles.
- **Markdown Support**: Renders code blocks, inline code, and text formatting.
- **Persistent History**: Conversations saved in browser localStorage.
- **Context Management**: Limits to 20 recent messages to avoid API limits.
- **Secure Proxy**: Backend server proxies requests to LM Studio, keeping API key server-side.
- **Real-time Status**: Shows response status and context usage.

## Prerequisites
- Python 3.x
- LM Studio running locally with a compatible model (e.g., `qwen/qwen3-4b-2507`)

## Installation
1. Clone or download this repository.
2. Install dependencies:
   ```bash
   pip install flask flask-cors requests
   ```

## Quickstart
1. Ensure LM Studio is running at `http://127.0.0.1:1234` with your desired model loaded.
2. Run the backend server:
   ```bash
   python server.py
   ```
3. Open your browser to `http://127.0.0.1:8080`.
4. Start chatting! The interface will proxy requests to LM Studio securely.

## Configuration
- **Model**: Update the `model` in `index.html` script if using a different LM Studio model.
- **API Key**: The key is hardcoded in `server.py` for demo purposes. In production, use environment variables.
- **Port**: Server runs on 8080 by default. Change in `server.py` if needed.
- **Context Limit**: Adjust `maxConversationLength` in `index.html` for more/less history.

## Notes
- The app uses OpenAI-compatible API format to communicate with LM Studio.
- Chat history persists across browser sessions but is stored locally.
- For production deployment, consider adding authentication and proper key management.

