# AI-Powered Resume Parser and Job Matcher

An AI-powered Python application that extracts information from resumes, analyzes job descriptions, and evaluates how closely candidates match a job role using Large Language Models (LLMs).

## Features

- **Job Description Parsing:** Extracts job roles, required skills, preferred skills, experience requirements, education requirements, and responsibilities.
- **Resume Parsing:** Extracts candidate details such as name, email, phone number, skills, experience, education, projects, and certifications.
- **Multiple File Formats:** Supports PDF and DOCX resumes.
- **AI-Based Matching:** Evaluates resumes against job requirements using an LLM.
- **Candidate Ranking:** Calculates match scores and ranks candidates.
- **Structured Data Validation:** Uses Pydantic to validate AI-generated responses.

## Tech Stack

- Python
- Groq API
- GPT-OSS-120B
- Pydantic
- PyPDF
- python-docx
- python-dotenv

## Project Structure

```text
resume-parser/
│
├── resumes/
│   ├── resume1.pdf
│   ├── resume2.pdf
│   └── resume3.docx
│
├── resume_parser.py
├── .env
├── .env.example
└── .gitignore
```

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install groq pydantic python-dotenv pypdf python-docx
```

### 4. Configure your environment variables

The actual `.env` file is not included in this repository because it contains private credentials.

Create a file named `.env` in the project root directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Replace `your_groq_api_key_here` with your own API key.

You can obtain an API key from the Groq Console:

https://console.groq.com/keys

**Important:** Never upload your actual `.env` file or API key to GitHub.

### 5. Add your resumes

Place your PDF and DOCX resume files inside the `resumes/` directory.

### 6. Run the application

```bash
python resume_parser.py
```

## How It Works

1. Loads the job description.
2. Sends the job description to the LLM for structured extraction.
3. Validates the extracted job requirements using Pydantic.
4. Reads PDF and DOCX resumes from the `resumes/` directory.
5. Extracts candidate information from each resume.
6. Validates the extracted resume data.
7. Compares each candidate's profile with the job requirements.
8. Generates match scores and ranks candidates.

## Environment Variables

| Variable | Description |
|---|---|
| `GROQ_API_KEY` | API key used to authenticate with Groq |

## Security

The repository should include a `.gitignore` file containing:

```gitignore
.env
.venv/
__pycache__/
*.pyc
```

The `.env.example` file can be committed safely because it contains only a placeholder:

```env
GROQ_API_KEY=your_groq_api_key_here
```

## Future Improvements

- Semantic resume matching using embeddings.
- Vector database integration for efficient candidate retrieval.
- OCR support for scanned resumes.
- Explainable candidate scoring.
- Web-based dashboard for recruiters.
- Duplicate resume detection.
- Improved candidate filtering.

## Disclaimer

This project is intended for educational and experimental purposes. AI-generated match scores are estimates and should not be used as the sole basis for recruitment decisions. Human review is necessary.

## Author

**Piyush Jha**

GitHub: [PiyushJha-dev-git]((https://github.com/PiyushJha-dev))
