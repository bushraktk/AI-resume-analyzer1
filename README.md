# 📄 ATS Resume Checker

A Streamlit app that scores a resume for Applicant Tracking System (ATS) compatibility and suggests concrete improvements, powered by Google Gemini Flash.

## Features
- Upload a resume as **PDF, DOCX or TXT**
- Optional **job description** for targeted keyword matching
- Overall **ATS score (0-100)** plus category scores (formatting, keywords, impact, skills, readability)
- Found vs. missing keywords
- Prioritised improvements with example rewrites
- Instant rule-based checks (contact info, sections, length, metrics)
- Download the report as JSON

## Run locally
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Get a free API key from [Google AI Studio](https://aistudio.google.com/apikey), then either:

- set it as an environment variable: `export GEMINI_API_KEY="your_key"` (Windows PowerShell: `$env:GEMINI_API_KEY="your_key"`), or
- create `.streamlit/secrets.toml` containing `GEMINI_API_KEY = "your_key"`, or
- paste it into the app sidebar.

```bash
streamlit run app.py
```

## Configuration
The model defaults to `gemini-flash-latest`. You can change it in the sidebar (e.g. `gemini-2.5-flash`).

## Notes
- Scanned/image-only PDFs have no extractable text. ATS systems can't read them either, so export a text-based PDF or DOCX.
- The score is an AI estimate, not the output of any real ATS. Use it as guidance.
- Never commit your API key. `.streamlit/secrets.toml` should be in `.gitignore`.

## Project structure
```
app.py            # Streamlit app
requirements.txt  # Dependencies
README.md
```
