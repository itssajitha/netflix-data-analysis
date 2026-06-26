# Netflix Movies and TV Shows — Exploratory Data Analysis

A mini data analysis project exploring the Netflix titles dataset using **pandas**, **numpy**, and **matplotlib**. The notebook walks through data inspection, content-type breakdown, upload trends over time, country and genre distributions, and visualization.

---

# Project Structure

```
.
├── notebook.ipynb          # Main analysis notebook
├── netflix_titles.csv.zip  # Netflix dataset (place in the same directory)
└── README.md
```

---

# Requirements

- Google Colab *(recommended)*, or Jupyter Notebook / JupyterLab locally
- Python 3.x
- pandas
- numpy
- matplotlib

These libraries come pre-installed on Google Colab — no setup needed there.
For local use, install with:

```bash
pip install pandas numpy matplotlib jupyter
```

---

# Dataset

The notebook expects a `netflix_titles.csv.zip` file — the Netflix titles dataset with columns such as `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in`, and `description`.

**On Google Colab:**
- Upload `netflix_titles.csv.zip` via the Files panel (left sidebar → Upload), **or**
- Mount Google Drive and update the `pd.read_csv()` path accordingly.

> ⚠️ Files uploaded directly to a Colab session are deleted when the runtime disconnects. Re-upload if you restart.

---

# What the Notebook Does

 1. Data Loading & Inspection
- Extracts `netflix_titles.csv` from the zip archive
- Loads it into a DataFrame with `pd.read_csv()`
- Inspects structure and previews the first few rows with `.head()`

 2. Data Quality Check
- Checks for missing values with `.isnull().sum()`
- Key nulls: `director` (2,634), `cast` (825), `country` (831), with minor gaps in `date_added`, `rating`, and `duration`
- Confirms dataset dimensions: **8,807 titles × 12 columns**

3. Content Type Distribution
- Counts Movies vs. TV Shows with `.value_counts()`
- 🥧 Pie chart showing the split (~70% Movies, ~30% TV Shows)

 4. Content Added Over Time
- Parses `date_added` into datetime and extracts the year
- 📊 Bar chart showing titles added per year — highlights Netflix's major content ramp-up from **2016 onwards**

 5. Top Content-Producing Countries
- Ranks the top 10 countries by number of titles
- 📊 Bar chart — **United States**, **India**, and **United Kingdom** lead

 6. Top Genres
- Explodes the multi-value `listed_in` column into individual genre entries
- 📊 Bar chart of the top 10 genres — **International Movies**, **Dramas**, and **Comedies** dominate

---

# How to Run

1. Open `notebook.ipynb` in [Google Colab](https://colab.research.google.com/)
2. Upload `netflix_titles.csv.zip` via the Files panel, or mount Google Drive and update the file path
3. Run all cells in order: **Runtime → Run all**

---

# Key Insights

- **Movies make up ~70%** of Netflix's catalog, with TV Shows accounting for the remaining ~30%.
- Netflix saw a **significant content surge from 2016**, peaking around 2019–2020.
- The **United States** dominates content production, followed by **India** and the **United Kingdom**.
- **International Movies**, **Dramas**, and **Comedies** are the three most represented genres on the platform.
- The `director` column has the highest number of missing values (2,634), which is expected as many TV Shows don't credit a single director.
