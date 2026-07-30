# DHd Blog Analysis

A reproducible Python workflow for collecting, processing, and analysing content from the **DHd Blog (Digital Humanities im deutschsprachigen Raum)**. This repository provides an end-to-end pipeline consisting of a web scraper, a curated dataset, and an exploratory analysis of publication trends, categories, tags, research topics, and textual characteristics.

---

## Repository Structure

```
dhd-blog-analysis/
│
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── .gitignore
│
├── data/
│   └── dhd_blog_dataset.xlsx
│
├── notebooks/
│   ├── dhd_blog_scraper.ipynb
│   └── dhd_blog_analysis.ipynb
│
├── figures/
│   ├── fig01_posts_per_year.png
│   ├── fig02_posts_per_month.png
│   └── ...
│
└── output/    (optional)
```

---

# Workflow

```
DHd Blog
    │
    ▼
Web Scraper
    │
    ▼
Raw HTML
    │
    ▼
Data Cleaning & Processing
    │
    ▼
Structured Dataset (.xlsx/.csv)
    │
    ▼
Exploratory Data Analysis
    │
    ├── Publication Trends
    ├── Category Analysis
    ├── Tag Analysis
    ├── Topic Analysis
    ├── Text Mining
    └── Visualizations
    │
    ▼
Research Figures & Insights
```

---

# Project Overview

This repository consists of two primary components.

## 1. DHd Blog Web Scraper

The scraper automatically collects publicly available posts from the DHd Blog by extracting:

- Publication date
- Title
- Author
- Categories
- Tags
- Number of comments
- Word count
- Full article text
- Archive metadata

The collected data are cleaned, standardized, and exported as structured Excel and CSV datasets.

The scraper is fully reproducible and can be rerun to update the dataset with newly published blog posts.

---

## 2. Exploratory Data Analysis

The analysis notebook investigates the collected dataset through descriptive statistics, text mining, and visual analytics, including:

- Publication trends over time
- Monthly publishing patterns
- Category distribution
- Category evolution
- Category co-occurrence
- Author statistics
- Tag frequencies
- Tag co-occurrence
- Word count analysis
- Dictionary-based research topic detection
- Topic evolution
- TF-IDF analysis
- Word clouds
- Bigrams
- Trigrams

Publication-quality figures are automatically generated and saved.

---

# Methodology

The project follows a reproducible workflow consisting of four stages.

### 1. Data Collection

Publicly available posts are collected automatically using a Python-based web scraper.

### 2. Data Processing

Extracted information is cleaned, standardized, and transformed into a structured dataset containing metadata and full article text.

### 3. Exploratory Data Analysis

The processed dataset is analysed using descriptive statistics, temporal analysis, category analysis, tag analysis, and text mining techniques.

### 4. Visualization

Publication-quality visualizations are generated to illustrate trends, distributions, relationships, and thematic patterns across the dataset.

---

# Dataset

Current dataset statistics:

- **2,740** DHd Blog posts
- Publication period: **2011–2026**

Each record contains:

- Post ID
- URL
- Publication date
- Author
- Categories
- Tags
- Number of comments
- Word count
- Full article text

---

# Outputs

Running the complete workflow produces:

- Cleaned Excel dataset
- Cleaned CSV dataset
- Publication-quality figures
- Statistical summaries
- Topic evolution analyses
- Text mining outputs
- Word clouds
- N-gram analysis

---

# Requirements

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---

# Usage

## Step 1 — Collect the dataset

Run:

```
notebooks/dhd_blog_scraper.ipynb
```

The scraper saves the processed dataset into:

```
data/
```

---

## Step 2 — Analyse the dataset

Run:

```
notebooks/dhd_blog_analysis.ipynb
```

Generated figures are automatically saved into:

```
figures/
```

---

# Technologies

This project uses:

- Python
- Pandas
- NumPy
- Matplotlib
- Requests
- BeautifulSoup
- NLTK
- WordCloud
- SciPy
- OpenPyXL
- Jupyter Notebook

---

# Reproducibility

The notebooks use relative paths and can be executed without modification in:

- Jupyter Notebook
- JupyterLab
- Visual Studio Code
- Google Colab
- GitHub Codespaces

---

# Data Source

The dataset was collected from publicly available posts on the **DHd Blog**.

https://dhd-blog.org/

---

# Future Work

Potential extensions include:

- Topic modelling (LDA or BERTopic)
- Named Entity Recognition (NER)
- Sentiment analysis
- Interactive dashboards
- Author and tag network analysis

---

# License

This project is distributed under the MIT License.

---

# Citation

If you use this repository in your research, please cite it using the citation information provided in `CITATION.cff`.

---

## Contact

Areesha Jiwani
M.Sc. Data Science Student

GitHub: https://github.com/areeshaj3109