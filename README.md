# DHd Blog Analysis

A reproducible Python workflow for collecting, processing, and analysing content from the **DHd Blog (Digital Humanities im deutschsprachigen Raum)**. This repository provides an end-to-end pipeline consisting of a web scraper, a curated dataset, and an exploratory analysis of publication trends, categories, tags, research topics, and textual characteristics.

---

## Repository Structure

```text
dhd-blog-analysis/
│
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── dhd_blog_dataset.csv
│   ├── dhd_blog_dataset.xlsx
│   ├── dhd_blog_all_post_links.csv
│   └── dhd_blog_post_errors.csv
│
├── notebooks/
│   ├── dhd_blog_scraper.ipynb
│   └── dhd_blog_analysis.ipynb
│
├── figures/
│   ├── fig01_dhd_posts_per_year.png
│   ├── fig02_posts_per_month.png
│   ├── fig03_top_dhd_blog_categories.png
│   └── ...
│
└── output/    (optional)
```

---

## Workflow

```text
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
Structured Dataset (.csv/.xlsx)
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

The scraper automatically collects publicly available blog posts from the DHd Blog by extracting:

- Publication date
- Title
- Author
- Categories
- Tags
- Number of comments
- Word count
- Full article text
- Archive metadata

The collected data are cleaned, standardized, and exported as structured CSV and Excel datasets.

The scraper supports checkpoint-based execution, allowing interrupted scraping runs to resume without repeating successfully collected articles.

The scraper can be rerun to update the dataset with newly published blog posts, provided the source website remains accessible and its HTML structure is compatible with the extraction logic.

**Website note:** During the November 2026 collection, the DHd Blog was temporarily served through static HTML pages. The scraper preserves the original discovered article URLs to maintain access to these pages.

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

Publicly available posts are collected automatically using a Python-based web scraper. Monthly archives and their paginated pages are traversed to discover article URLs, with unique post IDs used to prevent duplicate records.

### 2. Data Processing

Extracted information is cleaned, standardized, and transformed into a structured dataset containing metadata and full article text.

### 3. Exploratory Data Analysis

The processed dataset is analysed using descriptive statistics, temporal analysis, category analysis, tag analysis, and text mining techniques.

Research topic detection uses predefined keyword dictionaries. Topic assignments are exploratory and may include multiple topics per article.

### 4. Visualization

Publication-quality visualizations are generated to illustrate trends, distributions, relationships, and thematic patterns across the dataset.

---

# Dataset

Current dataset statistics (November 2026):

- **2,779** successfully scraped DHd Blog posts
- **2,780** unique discovered post links
- **1** excluded temporary website announcement
- **18** dataset columns
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
- Archive metadata

**Dataset format:** `dhd_blog_dataset.csv` is the primary full-text dataset used for analysis. The Excel version is provided for convenient inspection, but article text exceeding Excel's 32,767-character cell limit may be truncated.

---

# Outputs

Running the complete workflow produces:

- Cleaned CSV dataset (primary reusable format)
- Cleaned Excel dataset (for convenient inspection)
- Complete list of discovered blog post URLs
- Error log for posts that could not be processed (if any)
- Publication-quality figures (saved in the `figures/` directory)
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

## Step 1 - Collect the dataset

Run:

```text
notebooks/dhd_blog_scraper.ipynb
```

The scraper saves the processed data into the `data/` directory, including the cleaned CSV and Excel datasets, a complete list of discovered blog post URLs, and an error log containing any posts that could not be processed.

```text
data/
```

Temporary checkpoint files are saved locally in the `notebooks/` directory to support resuming interrupted scraping runs. These files are excluded from Git version control.

---

## Step 2 - Analyse the dataset

Run:

```text
notebooks/dhd_blog_analysis.ipynb
```

The analysis notebook uses `data/dhd_blog_dataset.csv` as its input to preserve complete article text.

Generated figures are automatically saved into:

```text
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

The notebooks use relative paths and are designed to run with the repository's folder structure in:

- Jupyter Notebook
- JupyterLab
- Visual Studio Code
- Google Colab
- GitHub Codespaces

The required dependencies must be installed before execution. Cloud-based environments such as Google Colab may require additional setup to make the repository files accessible.

For a complete run, execute the scraper notebook first, followed by the analysis notebook. The analysis notebook can also be run independently using the existing CSV dataset.

Scraping results depend on the availability and structure of the source website.

---

# Data Source

The dataset was collected from publicly available posts on the **DHd Blog**.

https://dhd-blog.org/

The dataset represents a snapshot of the website at the time of collection. Changes to the source website may affect future scraping results.

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

This project's original source code is distributed under the MIT License. See [LICENSE](LICENSE).

---

# Citation

If you use this repository in your research, please cite it using the citation information provided in `CITATION.cff`.

---

## Contact

Areesha Jiwani  
M.Sc. Data Science Student

GitHub: https://github.com/areeshaj3109
