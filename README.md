# AI-Powered Job Recommendation System

An end-to-end AI system that analyzes a candidate’s resume and recommends the most relevant job roles using semantic similarity. The system combines NLP, sentence embeddings, and vector search to match resumes with job postings efficiently.

## Features
- Resume parsing from PDF files
- Semantic job matching using Sentence Transformers
- High-performance similarity search with FAISS
- Hybrid filtering using TF-IDF + dense embeddings
- Interactive web interface built with Streamlit
- Cached embeddings for fast repeated queries

## Tech Stack
- Python
- Streamlit
- SentenceTransformers (MiniLM)
- FAISS
- PyTorch
- Scikit-learn
- Pandas, NumPy
- PyMuPDF (PDF text extraction)

## Project Architecture
```
job_recommendation_system/
├── requirements.txt
├── raw_data/
│   ├── companies/
│   │   ├── companies.csv
│   │   ├── company_industries.csv
│   │   ├── company_specialities.csv
│   │   └── employee_counts.csv.csv
│   ├── jobs/
│   │   ├── benefits.csv
│   │   ├── job_industries.csv
│   │   ├── job_skills.csv
│   │   └── salaries.csv.csv
│   ├── mappings/
│   │   ├── industries.csv
│   │   └── skills.csv
│   └── postings.csv
├── Data_Cleaning.ipynb
├── JobsFE.csv
├── model.py
├── streamlit.py
└── README.md
```

## How It Works
1. User uploads a resume in PDF format
2. Text is extracted from the resume
3. Resume is converted into a semantic embedding
4. Job postings are filtered using TF-IDF
5. FAISS performs vector similarity search
6. Top matching jobs are displayed in the UI

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/shashican17/ai_based_job_recommendation_system
cd ai-job-recommendation-system-main
```

### 2. Create and Activate Virtual Environment
```bash
python -m venv venv
venv\Scripts\Activate   # Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Application
```bash
streamlit run streamlit.py
```
Open http://localhost:8501 in your browser.

## Dataset
The job dataset is derived from a large-scale job postings corpus and cleaned using a custom preprocessing pipeline.
Text fields include job title, responsibilities, skills, location, and work mode.

## Performance Notes
- First run may take a few minutes to generate embeddings
- Subsequent runs load instantly using cached embeddings
- Optimized for CPU-only environments
