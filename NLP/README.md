🧠 AI Interview Preparation Suite

ATS + HR/Tech Questions + MCQs + Timed Practice + JD Analyzer + Voice Interview + Resume Rewriter + Full PDF Report

This project is a complete AI-powered interview preparation system designed for job seekers, students, and professionals.
It integrates LLMs, NLP, ATS scoring, voice analysis, and resume rewriting into a unified interface built with Streamlit.

🚀 Key Features
✅ 1. ATS Resume Scanner

Upload your PDF resume

Extracts skills (spaCy + rule-based NLP)

Matches your skills with target job roles

Generates an ATS match score

AI-powered resume improvement suggestions

✅ 2. HR & Technical Question Generator

AI-based question generation (FLAN-T5 or similar LLM)

OR fallback traditional question banks

Difficulty levels: Beginner, Intermediate, Advanced

AI-generated answers for every question

Duplicate-free generation (built-in dedup engine)

✅ 3. MCQ Generator (AI + Static Hybrid)

AI MCQ generator with explanations

Static MCQ fallback for reliability

Difficulty mix:

30% Easy

50% Intermediate

20% Advanced

Deduplication applied to avoid repeat questions

Score tracking + analytics

✅ 4. Practice Mode (Timed)

Professional timed test mode

30–60 questions

Per-question timer

Auto-submission on timeout

Detailed performance breakdown

✅ 5. Job Description (JD) Analyzer

Upload a JD OR paste raw text.
The system will:

✅ Extract must-have skills
✅ Extract optional/nice-to-have skills
✅ Generate a JD summary
✅ Compare your resume skills vs JD skills
✅ Identify missing keywords

This is extremely useful for tailoring resumes.

✅ 6. AI Voice Interview (Simulated HR Round)

AI interviewer asks questions (text + TTS voice output)

User uploads an audio answer

Audio is transcribed (Speech-to-Text)

AI evaluates answer:

✅ Clarity
✅ Structure
✅ Depth
✅ Relevance
✅ Usage of metrics

Provides feedback & actionable tips

✅ 7. Resume Rewriter (AI-Powered)

Helps you rewrite:

✅ Experience bullets
✅ Achievements
✅ Impact statements

Also includes:

✅ Keyword Infusion — add missing JD keywords naturally into text
✅ Target-role optimization

✅ 8. Analytics Dashboard

Visual summary of:

MCQ correctness

Score distribution

Difficulty scores

Study progress

✅ 9. PDF Export

Generate a complete report containing:

✅ HR questions + answers
✅ Technical questions + answers
✅ MCQs + explanations
✅ ATS score
✅ JD analysis
✅ Resume suggestions
✅ Voice interview transcript + feedback
✅ Practice mode summary
✅ Analytics

Perfect for offline practice or review.

📁 Project Structure
project/
│
├── app.py                         # Main Streamlit application
│
├── config/
│   └── roles.py                   # Role definitions, difficulty settings
│
├── modules/
│   ├── resume_parser.py
│   ├── ats_scoring.py
│   ├── question_generator.py
│   ├── answers.py
│   ├── mcq_generator.py
│   ├── mcq_ai_generator.py
│   ├── scoring.py
│   ├── timer.py
│   ├── pdf_export.py
│   ├── dedup.py
│   ├── voice_interview.py
│   ├── jd_analyzer.py
│   └── resume_rewriter.py
│
└── requirements.txt               # All dependencies

🛠️ First-Time Setup & Installation

Follow these steps to set up the application on your system for the first time:

## Prerequisites

- **Python 3.8 or higher** (check with `python --version` or `python3 --version`)
- **pip** (usually comes with Python)
- **Git** (if cloning from repository)
- **Internet connection** (for downloading dependencies and models)

---

## Step-by-Step Installation Guide

### Step 1: Download or Clone the Project

**Option A: If you have the project folder already:**
- Navigate to the project folder in your terminal/command prompt
- Skip to Step 2

**Option B: Clone from Git (if available):**
```bash
git clone https://github.com/yourusername/ai-interview-suite
cd ai-interview-suite
```

### Step 2: Create a Virtual Environment

**Why?** A virtual environment isolates project dependencies and prevents conflicts with other Python projects.

**Windows:**
```bash
python -m venv venv
```

**Mac/Linux:**
```bash
python3 -m venv venv
```

This creates a `venv` folder in your project directory.

### Step 3: Activate the Virtual Environment

**Windows (Command Prompt):**
```bash
venv\Scripts\activate
```

**Windows (PowerShell):**
```bash
venv\Scripts\Activate.ps1
```
*(If you get an execution policy error, run: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`)*

**Mac/Linux:**
```bash
source venv/bin/activate
```

✅ **Success indicator:** You should see `(venv)` at the beginning of your terminal prompt.

### Step 4: Install Python Dependencies

Install all required packages:
```bash
pip install -r requirements.txt
```

⏱️ **Note:** This may take 5-10 minutes depending on your internet speed, especially for `torch` and `transformers` packages.

### Step 5: Install spaCy Language Model

Download the English language model for NLP features:
```bash
python -m spacy download en_core_web_sm
```

✅ **Verification:** You should see "✔ Download and installation successful" message.

### Step 6: Verify Installation (Optional but Recommended)

Test that key modules can be imported:
```bash
python -c "import streamlit; import spacy; import pandas; print('All core packages installed successfully!')"
```

### Step 7: Run the Application

Start the Streamlit application:
```bash
streamlit run app.py
```

✅ **Success:** Your default web browser should automatically open with the application running at `http://localhost:8501`

If the browser doesn't open automatically, copy the URL shown in the terminal and paste it into your browser.

---

## First Run Checklist

After the app launches, you should see:

- ✅ ATS Resume Scanner tab
- ✅ HR & Technical Question Generator tab
- ✅ MCQ Generator tab
- ✅ Practice Mode tab
- ✅ JD Analyzer tab
- ✅ Voice Interview tab
- ✅ Resume Rewriter tab
- ✅ Analytics Dashboard tab
- ✅ PDF Export option

---

## Troubleshooting

### Issue: "Python is not recognized"
- **Solution:** Make sure Python is installed and added to your system PATH. Download from [python.org](https://www.python.org/downloads/)

### Issue: "pip is not recognized"
- **Solution:** Reinstall Python and make sure to check "Add Python to PATH" during installation

### Issue: "ModuleNotFoundError" for any package
- **Solution:** Make sure your virtual environment is activated (you see `(venv)` in terminal), then run:
  ```bash
  pip install -r requirements.txt
  ```

### Issue: "spacy: command not found" or spaCy model download fails
- **Solution:** Ensure spaCy is installed first (`pip install spacy`), then retry:
  ```bash
  python -m spacy download en_core_web_sm
  ```

### Issue: App runs but AI features don't work
- **Note:** AI features (LLM-based question generation) require `transformers` and `torch`. These are large packages.
- **Fallback:** The application has built-in fallback mechanisms and will use traditional question banks if AI models are unavailable.

### Issue: Port 8501 is already in use
- **Solution:** Streamlit will automatically use the next available port, or stop other Streamlit apps running on that port.

---

## Stopping the Application

- Press `Ctrl + C` in the terminal where Streamlit is running
- The application will shut down and you'll return to the command prompt

---

## Next Steps

1. **Upload a Resume (PDF)** - Try the ATS Resume Scanner
2. **Generate Questions** - Test the HR & Technical Question Generator
3. **Upload a Job Description** - Use the JD Analyzer to compare your resume
4. **Try Practice Mode** - Test your knowledge with timed MCQs
5. **Export PDF Report** - Generate a comprehensive report of your practice session

---

## Running the Application Again (After First Setup)

Once set up, you only need:

1. Navigate to the project folder
2. Activate virtual environment: `venv\Scripts\activate` (Windows) or `source venv/bin/activate` (Mac/Linux)
3. Run: `streamlit run app.py`

🤖 Technologies Used

Streamlit (UI)

Python

spaCy (NLP)

Transformers / FLAN-T5 (LLM)

SpeechRecognition (STT)

gTTS / pyttsx3 (TTS)

ReportLab (PDF)

Pandas (Analytics)

spaCy NER (Skill Extraction)

📌 Future Enhancements

Live microphone support (no upload needed)

Leaderboards & gamified scoring

Multi-language interview support

Chrome extension to analyze job postings directly from LinkedIn

❤️ Contributing

PRs are welcome!
Improve modules, add MCQs, or enhance LLM prompts.

📄 License

MIT License — free to use, modify, and distribute.