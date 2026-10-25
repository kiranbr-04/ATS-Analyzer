# ATS Resume Analyzer

A simple browser-based tool for checking how well a resume matches a job description using an ATS-style keyword analysis.

## Overview

This project is a lightweight web app that helps job seekers quickly compare their resume against a target job description and get a score along with actionable suggestions.

It includes:
- User registration and login flow
- Resume upload support for `.txt` and `.pdf` files
- Manual resume text entry
- Job description input
- ATS match scoring based on keyword overlap
- Recommendations for improving resume alignment
- Responsive dark-themed UI

## Why this project exists

Many resumes are rejected by applicant tracking systems (ATS) because they do not include enough relevant keywords from the job description. This tool is designed to give a quick, practical estimate of match quality before submitting an application.

## Features

### User authentication
The app uses browser `localStorage` to store registered users and the currently logged-in user. This makes the project easy to run without a backend or database.

### Resume analysis
The analyzer compares:
- Keywords from the job description
- Keywords from the resume text

It calculates:
- Overall ATS score
- Keyword match percentage
- Suggestions for improving the resume

### File support
Users can upload:
- `.txt` files
- `.pdf` files (parsed through PDF.js)

### Suggestions
The app provides simple guidance such as:
- Add missing job-related keywords
- Expand resume details for experience and achievements
- Ensure key sections like Skills, Experience, and Education are present

## Project structure

```text
ATS-Analyzer/
├── index.html        # Login and registration page
├── analyzer.html     # Resume analysis interface
├── README.md         # Project documentation
```

## How to run

### Option 1: Open directly in browser
1. Open `index.html` in your browser.
2. Register a new account or log in.
3. Navigate to the analyzer page.
4. Paste a job description and resume text, or upload a resume file.
5. Click `Analyze Resume`.

### Option 2: Serve locally
If you want to run it from a local web server:

```bash
cd ATS-Analyzer
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/index.html
```

## How the scoring works

The app uses a simple ATS-style heuristic:
- Extracts words from the job description
- Extracts words from the resume
- Finds overlapping keywords
- Calculates a percentage match
- Produces a weighted score and recommendations

This is a demo-style scoring method, not a professional ATS engine.

## Notes

- This project is frontend-only and stores user data in the browser.
- It is intended for learning and demo purposes.
- For real-world hiring workflows, a production system would typically include backend authentication, secure storage, and more advanced parsing and ranking.

## Example use case

A candidate applies for a software engineering role:
- Pastes the job description into the app
- Uploads their resume as a PDF
- Receives an ATS score and suggestions
- Updates their resume with missing keywords like `JavaScript`, `React`, `API`, and `Agile`

## License

This project is intended for educational and personal use. If you are using it in a team or production environment, it is recommended to add a license that matches your organization’s policies.
