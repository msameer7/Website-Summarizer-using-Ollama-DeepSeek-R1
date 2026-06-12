# Website Summarizer using Ollama & DeepSeek-R1

A simple AI-powered website summarization tool that scrapes website content and generates concise summaries using a locally running Large Language Model (LLM) through Ollama.

This project demonstrates the fundamentals of:

* Web Scraping with BeautifulSoup
* Prompt Engineering
* Local LLM Inference with Ollama
* Website Content Summarization
* OpenAI-Compatible API Usage

## Features

* Extracts textual content from any website
* Removes irrelevant elements such as:

  * Scripts
  * Styles
  * Images
  * Input fields
* Uses a local DeepSeek-R1 8B model through Ollama
* Generates concise website summaries
* Supports humorous and customized response styles via system prompts
* Runs completely locally without requiring paid API credits

## Project Structure

```text
project/
│
├── main.py
├── scraper.py
└── README.md
```

### main.py

Responsible for:

* Connecting to Ollama
* Creating prompts
* Sending requests to the LLM
* Generating website summaries

### scraper.py

Responsible for:

* Fetching website content
* Parsing HTML using BeautifulSoup
* Removing irrelevant page elements
* Extracting clean text
* Extracting website links

## Requirements

Install the required packages:

```bash
pip install requests beautifulsoup4 openai
```

## Install Ollama

Download and install Ollama:

https://ollama.com

Pull the DeepSeek-R1 model:

```bash
ollama pull deepseek-r1:8b
```

Start Ollama:

```bash
ollama serve
```

Verify that Ollama is running:

```bash
http://localhost:11434
```

## Usage

### Import Dependencies

```python
from openai import OpenAI
from scraper import fetch_website_contents
```

### Configure Ollama

```python
OLLAMA_BASE_URL = "http://localhost:11434/v1"

ollama = OpenAI(
    base_url=OLLAMA_BASE_URL,
    api_key="ollama"
)
```

### Generate Summary

```python
display_summary("https://quotes.toscrape.com/")
```

Example output:

```markdown
This website is a collection of famous quotes ranging from inspirational wisdom to humorous observations on life. Content is organized through simple tags such as life, love, humor, and inspiration. The site offers a straightforward browsing experience for quote enthusiasts while keeping things pleasantly simple.
```

## How It Works

```text
Website URL
      │
      ▼
Web Scraper
      │
      ▼
Clean Extracted Text
      │
      ▼
Prompt Construction
      │
      ▼
DeepSeek-R1 via Ollama
      │
      ▼
Generated Summary
```

## Future Improvements

* Multi-page website summarization
* Streamlit web interface
* Gradio application
* Retrieval-Augmented Generation (RAG)
* Vector database integration
* Website comparison functionality
* Sentiment analysis
* News extraction and summarization
* Agent-based workflows

## Learning Objectives

This project is ideal for anyone learning:

* AI Engineering
* LLM Engineering
* Prompt Engineering
* Local AI Development
* Web Scraping
* Generative AI Applications

## Author

Muhammad Sameer

Built while learning AI Engineering and LLM Engineering with Ollama, DeepSeek-R1, and Python.
