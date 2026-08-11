# Resume ↔ Job Match — The Screening Room

A browser-based resume and job description matching tool that analyzes how closely a resume aligns with a job posting. It detects overlapping skills, highlights missing skills, calculates content similarity using TF-IDF cosine similarity, and presents an overall match score.

## Features

- **Resume & Job Description Input**
  - Paste resume and job description text directly into the app.
  - Upload `.txt` files or drag and drop them into the input panels.

- **Skill Matching**
  - Detects skills using a curated taxonomy of approximately 150 common terms.
  - Covers programming, data & analytics, cloud & DevOps, design & product, business, project management, tools, HR/operations, and soft skills.
  - Separates skills into:
    - Matched skills
    - Missing skills
    - Extra skills found only on the resume

- **ATS-Style Match Score**
  - Calculates skill coverage based on skills detected in the job description.
  - Calculates full-text similarity using TF-IDF cosine similarity.
  - Overall score:
    - 65% Skill Coverage
    - 35% Content Similarity

- **Category Breakdown**
  - Shows match performance across relevant skill categories.

- **Highlighted Comparison**
  - Highlights matched and extra skills in the resume.
  - Highlights matched and missing skills in the job description.

- **Preset Examples**
  - Includes sample Data Analyst and Product Marketing scenarios for quick testing.

- **Responsive Interface**
  - Works across desktop and smaller screen sizes.

## How It Works

The application follows a simple browser-based analysis pipeline:

1. Enter or upload a resume.
2. Enter or upload a job description.
3. Extract recognized skills from both texts using the built-in taxonomy.
4. Compare the detected skill sets.
5. Calculate skill coverage.
6. Calculate TF-IDF cosine similarity between the two documents.
7. Combine the two scores into the overall match score.
8. Display matched, missing, and extra skills along with highlighted text.

### Scoring

The application uses:

```text
Overall Match = 65% × Skill Coverage + 35% × Content Similarity
```

Where:

```text
Skill Coverage = Matched JD Skills / Total JD Skills × 100
```

Content similarity is calculated using TF-IDF-weighted term vectors and cosine similarity.

## Tech Stack

- **HTML5**
- **CSS3**
- **Vanilla JavaScript**
- **TF-IDF**
- **Cosine Similarity**
- **Regular Expressions**
- **FileReader API**
- **Responsive CSS Grid/Flexbox**

No backend or external machine-learning API is required for the current implementation.

## Project Structure

```text
resume-jd-matcher/
│
└── resume-jd-matcher.html
```

The current implementation is contained in a single HTML file with the UI, styling, skill taxonomy, analysis logic, and file-upload functionality.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/resume-jd-matcher.git
cd resume-jd-matcher
```

### 2. Open the application

Open the HTML file directly in a modern web browser:

```text
resume-jd-matcher.html
```

Alternatively, use VS Code with the Live Server extension for local development.

### 3. Analyze a Resume

- Paste your resume into **Your Resume**.
- Paste the target job posting into **Job Description**.
- Click **Run the match →**.
- Review the score, category breakdown, matched skills, missing skills, extra skills, and highlighted comparison.

## Example Use Case

A candidate applying for a Data Analyst position can compare their resume against a job description requiring skills such as:

- Python
- SQL
- Tableau
- A/B Testing
- Predictive Modeling
- Data Warehousing
- Communication

The application identifies which of these skills appear in the resume and ranks missing skills according to their frequency in the job description.

## Methodology & Limitations

The current implementation intentionally uses a lightweight, transparent matching approach.

### Skill Detection

Skills are detected against a curated taxonomy of approximately 150 common terms using exact word/phrase matching rather than a semantic AI model.

This means that:

- The taxonomy is not exhaustive.
- Synonyms or equivalent skills may not always be recognized.
- The tool cannot determine actual proficiency.
- The tool cannot verify whether a claimed skill is genuine.

### TF-IDF Similarity

The application calculates TF-IDF cosine similarity between the resume and job description.

Because only two documents are compared, the IDF calculation is a simplified implementation rather than a corpus-trained information-retrieval system.

### ATS Score

The score should be treated as an **analysis and resume-tailoring aid**, not as a prediction of how a real company's ATS or recruiter will evaluate a candidate.

## Privacy

The current implementation performs its analysis in the browser. The uploaded `.txt` content is read using the browser's `FileReader` API and processed by the client-side JavaScript.

## Future Improvements

Potential improvements include:

- PDF and DOCX resume parsing
- Semantic similarity using Sentence Transformers
- Improved skill/entity extraction
- Experience and seniority matching
- Education requirement matching
- Job-title similarity
- Resume improvement recommendations
- Keyword optimization suggestions
- Exportable PDF analysis reports
- Backend API for persistent analysis
- Dashboard for tracking multiple job applications

## Author

**Vatsal Sharma**

Computer Science / Software Development & Data Science

GitHub: https://github.com/vatsalsharma1234

## License

This project is intended for educational and portfolio purposes.
