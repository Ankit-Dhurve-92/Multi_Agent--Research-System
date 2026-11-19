<<<<<<< HEAD
# ResearchMind — Multi-Agent Research System

ResearchMind is an AI-powered research assistant that uses a multi-agent workflow to search the web, read relevant pages, write a structured research report, and critique the generated report.

The project includes a Streamlit web interface and a command-line pipeline.

## Features

- **Search Agent:** Uses Tavily to find recent web information and return titles, URLs, and snippets.
- **Reader Agent:** Selects a relevant URL from the search results and extracts page text.
- **Writer Chain:** Uses an OpenAI chat model to create a structured research report.
- **Critic Chain:** Reviews the report and returns a score, strengths, areas to improve, and a verdict.
- **Streamlit UI:** Provides a web interface to enter a topic, view pipeline results, and download the report as a Markdown file.
- **CLI mode:** Run the research pipeline directly from the terminal.

## Workflow

```text
Research Topic
     |
     v
Search Agent (Tavily)
     |
     v
Reader Agent (Web-page extraction)
     |
     v
Writer Chain (Research report)
     |
     v
Critic Chain (Review and score)
     |
     v
Final Report + Critic Feedback
```

## Tech Stack

- Python
- LangChain
- LangChain OpenAI integration
- OpenAI API (`gpt-4o-mini`)
- Tavily Search API
- Streamlit
- Requests and Beautiful Soup

## Project Structure

```text
Multi-agent-research-system/
├── agents.py          # Search/reader agents, writer chain, critic chain
├── app.py             # Streamlit web application
├── pipeline.py        # Command-line research pipeline
├── tools.py           # Tavily web search and URL scraping tools
├── requirements.txt   # Python dependencies
├── .env               # API keys (create this file; do not commit it)
├── .gitignore         # Files excluded from Git
└── README.md          # Project documentation
```

## Prerequisites

- Python 3.10 or newer
- An OpenAI API key
- A Tavily API key
- Internet connection

Create API keys through the official provider websites:
- OpenAI: https://platform.openai.com/api-keys
- Tavily: https://app.tavily.com/

API usage may incur charges according to the providers' pricing and account limits.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
```

Replace the URL and folder name with your GitHub repository details.

### 2. Create and activate a virtual environment

**Windows PowerShell**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation scripts, you can use the environment's Python directly:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

Or use Command Prompt activation:

```cmd
.venv\Scripts\activate.bat
```

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m pip install streamlit
```

`streamlit` is required by `app.py`; add it to `requirements.txt` if it is not already listed.

### 4. Configure environment variables

Create a file named `.env` in the project root:

```env
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Replace the placeholder values with your own API keys. **Never upload `.env` or expose API keys in source code, screenshots, or commits.**

## Run the Application

### Streamlit web interface

```bash
streamlit run app.py
```

Streamlit will print a local URL (usually `http://localhost:8501`) in the terminal. Open it in your browser.

Enter a research topic and start the workflow. The application displays search output, extracted page content, the generated report, and critic feedback. You can download the report as a Markdown file.

### Command-line interface

```bash
python pipeline.py
```

Enter a research topic when prompted. The pipeline runs the search, reader, writer, and critic stages and prints the results in the terminal.

## Environment Variables

| Variable | Purpose |
|---|---|
| `OPENAI_API_KEY` | Authenticates requests to the OpenAI model used by the writer and critic, and by the agents. |
| `TAVILY_API_KEY` | Authenticates web-search requests through Tavily. |

## Important Notes and Limitations

- The project currently configures the OpenAI model as `gpt-4o-mini` in `agents.py`.
- Search results and scraped page content depend on external services and website availability.
- Some websites may block automated requests or return incomplete content.
- The reader currently extracts text from a selected URL and limits the returned content to approximately 3,000 characters.
- The generated report should be checked against its cited source URLs before being used for academic or professional decisions.
- API calls require valid provider credentials and may be subject to rate limits and usage costs.

## Security

Before pushing the project to GitHub, ensure that `.env`, virtual environments, Python cache files, and other private or generated files are excluded.

A suggested `.gitignore`:

```gitignore
.env
.env.*
!.env.example
.venv/
venv/
__pycache__/
*.py[cod]
.vscode/
.DS_Store
Thumbs.db
```

You may optionally commit an `.env.example` file containing only placeholder values:

```env
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Do not put real credentials in `.env.example`.

## Future Improvements

- Add source verification and stronger citation handling.
- Allow users to review or choose sources before scraping.
- Add retry handling, timeouts, and clearer error reporting for API failures.
- Store research history and support report export formats such as PDF.
- Add automated tests and configurable model settings.

## Author


Ankit Dhurve
Roll No. - 25210019
---

*Built with LangChain, OpenAI, Tavily, and Streamlit.*
=======
# Multi-Agen-For-Research-
>>>>>>> a18a08418a9ace49bb1fd7ec0fb5cc66913f322f
