AI Stock Analysis Assistant - Backend

This is the backend service for the AI Stock Analysis Assistant. It provides a FastAPI server that integrates with LangChain and Yahoo Finance to offer an intelligent interface for querying stock market data.

Features

This application offers a comprehensive set of features for stock analysis:

AI-Powered Chat Interface: Interact with an intelligent agent to ask questions about stocks using natural language.

Real-Time Stock Prices: Fetch up-to-the-minute stock prices for any public company using their ticker symbol.

Historical Data Analysis: Retrieve and analyze historical stock performance over specific date ranges.

Financial Statements: Access company balance sheets to understand their financial health.

Latest News Integration: Get the latest news and headlines for specific stocks to stay informed about market-moving events.

Streaming Responses: Enjoy a fluid user experience with real-time streaming responses from the AI agent.

Memory & Context: The agent retains context within a thread, allowing for follow-up questions and more complex interactions.


Prerequisites

Python 3.12 or higher

uv (recommended) or pip for package management


Installation

1. Navigate to the backend directory:

cd backend


2. Install dependencies:

Using uv (Recommended):

uv sync

Or using standard pip:

pip install -r pyproject.toml  
# Note: You might need to manually install dependencies listed in pyproject.toml if not using a tool that supports it directly, or create a requirements.txt  
pip install fastapi "langchain[openai]" pydantic python-dotenv uvicorn yfinance


3. Environment Configuration:
Create a .env file in the backend directory. You will likely need API keys for the AI service provider being used.

# Example .env content  
OPENAI_API_KEY=your_api_key_here



Running the Application

To start the backend server, run the following command:

uvicorn main:app --host 0.0.0.0 --port 8888 --reload

The API will be available at http://localhost:8888.

API Endpoints

GET /: Health check endpoint. Returns a message confirming the backend is running.

POST /api/chat: Main chat endpoint. Accepts a JSON payload with the user's prompt and thread ID, and returns a streaming response.


Technology Stack

Framework: FastAPI

AI/LLM orchestration: LangChain, LangGraph

Data Source: yfinance (Yahoo Finance)

Server: Uvicorn 
