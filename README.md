# Remote Job Market Intelligence Pipeline
 
An end-to-end data pipeline that scrapes, cleans, and analyzes remote tech job listings from Remote OK to surface skill demand trends, hiring patterns, and role distributions across the remote job market.
 
![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?logo=pandas)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup4-scraping-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
 
---
 
## What This Project Does
 
Most job market analyses rely on aggregated survey data. This project pulls directly from live job listings — extracting, cleaning, and analyzing real postings to answer questions recruiters and job seekers actually care about:
 
- Which skills appear most frequently in remote tech roles?
- What job types dominate the remote market?
- Which companies post the most remote roles?
- How does skill demand vary across role categories?
---
 
## Key Findings
 
- **Python, SQL, AWS, and JavaScript** are the four highest-demand skills across all remote tech listings
- Fully remote roles account for the majority of postings — location-flexible listings are a small minority
- Technical roles (Engineering, Data, DevOps) dominate Remote OK's listing volume
- A small number of companies account for a disproportionate share of remote job postings
> Full analysis with charts: [`notebooks/analysis.ipynb`](notebooks/analysis.ipynb)  
> Methodology and approach: [`docs/methodology.md`](docs/methodology.md)
 
---
 
## Pipeline Architecture
 
```
Raw HTML (Remote OK)
        ↓
   [ Scraper ]          — requests + BeautifulSoup, rate-limited
        ↓
  [ Data Cleaner ]      — deduplication, null handling, standardization
        ↓
   [ Analyzer ]         — skill frequency, role distribution, trend analysis
        ↓
 [ Visualizations ]     — Matplotlib + Seaborn charts
        ↓
   [ Report ]           — findings and recommendations
```
 
---
 
## Ethical Scraping Compliance
 
This project follows responsible scraping practices:
 
- `robots.txt` reviewed and respected before scraping
- 1-second crawl delay between all requests
- Forbidden endpoints avoided
- No parallel or automated bot scraping
- Raw scraped data not published publicly
- Data used strictly for analysis and educational purposes
---
 
## Tech Stack
 
| Layer | Tools |
|---|---|
| Scraping | Python, requests, BeautifulSoup4 |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Environment | Jupyter Notebook, VS Code |
| Version Control | GitHub |
 
---
 
## Project Structure
 
```
remoteok-market-intelligence/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── src/
│   ├── scraper.py           # Ethical scraping logic with rate limiting
│   ├── data_cleaner.py      # Cleaning pipeline
│   └── analyzer.py          # Analysis and visualization functions
│
├── notebooks/
│   └── analysis.ipynb       # Full EDA with findings and charts
│
├── data/
│   └── cleaned/
│       └── remoteok_jobs_cleaned.csv
│
├── visualizations/
│   ├── top_skills.png
│   ├── job_type_distribution.png
│   ├── top_job_titles.png
│   └── skill_frequency_comparison.png
│
└── docs/
    └── methodology.md       # Technical approach and decisions
```
 
---
 
## Setup and Usage
 
```bash
# Clone the repository
git clone https://github.com/asad-haris/remoteok-market-intelligence
cd remoteok-market-intelligence
 
# Install dependencies
pip install -r requirements.txt
 
# Run the scraper
python src/scraper.py
 
# Run analysis
jupyter notebook notebooks/analysis.ipynb
```
 
---
 
## Screenshots

<img width="2967" height="1773" alt="top_skills" src="https://github.com/user-attachments/assets/c655ac74-ab1a-425a-ba98-0d9728187a43" />

<!-- Add 2-3 screenshots of your visualizations here -->
<!-- Example: -->
<!-- ![Top Skills](visualizations/top_skills.png) -->
<!-- ![Job Type Distribution](visualizations/job_type_distribution.png) -->
 
---
 
## Limitations
 
- Data sourced exclusively from Remote OK — does not represent the full global remote job market
- Salary and experience level data not available in public listings
- Dataset reflects a specific scraping window — trends may shift over time
- Analysis is descriptive; predictive modeling not applicable to this dataset structure
---
 
## License
 
MIT License — free to use with attribution.
 
