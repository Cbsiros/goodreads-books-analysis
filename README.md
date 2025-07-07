# 📚 Goodreads Book Scraper & Analyzer

A two-stage data pipeline that scrapes detailed metadata from Goodreads' ["Best Books Ever"](https://www.goodreads.com/list/show/1.Best_Books_Ever) list, cleans and transforms it into structured datasets, and prepares it for data analysis, visualization, and machine learning workflows.

---

## 🔍 Project Overview

This project collects and prepares real-world book data by:

- 🌐 **Scraping Goodreads** for book-level details  
- 🧼 **Cleaning and transforming** raw metadata into analysis-ready format  
- 🧠 **Engineering features** like `book_age` and `author_popularity`  
- 📊 **Normalizing genres** into a one-hot encoded matrix  
- 🧪 **Generating EDA summaries** to assess data quality and structure  

---

## 📁 Output Files

| File                                | Description                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------|
| `goodreads-books-raw.csv`           | Raw scraped metadata for each book (overwritten on every scrape run)       |
| `goodreads-books-clean.csv`         | Cleaned, structured dataset with `book_id`, feature engineering, and imputed values |
| `goodreads-book-genres-clean.csv`   | One-hot encoded genre matrix aligned to `book_id`                           |

---

## 🔧 Full Pipeline Features

### ✅ Stage 1: Web Scraping (`data-collection.ipynb`)

- Collects links from multiple Goodreads list pages  
- Extracts metadata: title, author, genres, rating, reviews, description, language, series, and cover image  
- Implements:
  - Retry logic for stability  
  - Custom User-Agent and request throttling  
  - Structured `Book` dataclass for clean data modeling  
  - Logging for tracking progress and errors  

### ✅ Stage 2: Cleaning, Transformation, and EDA (`data-cleaning.ipynb`)

- Assigns a unique `book_id` to every book  
- Cleans whitespace in `title`, `author`, `description`  
- Converts `num_pages` and `publication_year` to integers  
- Removes duplicates based on `title` and `author`  
- Imputes missing `language` values using the `langid` library  
- Normalizes and one-hot encodes `genres` into a separate matrix  
- Engineers:
  - `book_age` from publication year  
  - `author_popularity` based on author frequency  
- Includes a custom `print_summary()` EDA tool for diagnostics  

---

## 🛠️ Technologies Used

- Python 3.x  
- Requests  
- BeautifulSoup4  
- Pandas / NumPy / SciPy  
- langid  
- Dataclasses  
- Jupyter Notebook  

---

## ⚙️ How to Use

1. **Clone the repository**  
2. *(Optional)* Create and activate a virtual environment  
3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
4. **Run the notebooks in order**:
    `data-collection.ipynb`
    `data-cleaning.ipynb`

Output files will be saved to the ./data/ directory

---

## ⚠️ Notes

- The raw data file (`goodreads-books-raw.csv`) is overwritten on every run to ensure freshness  
- This project follows respectful scraping practices:
  - Custom User-Agent  
  - Throttled requests with random delays  
- Always respect [Goodreads’ Terms of Use](https://www.goodreads.com/about/terms)  

---

## 📈 Next Steps

Planned enhancements include:

- 🧠 NLP-based topic modeling and sentiment analysis  
- 📊 Power BI or interactive dashboard for visual exploration  
- 🔍 Clustering authors or genres by themes or popularity  
- 🤖 Book recommendation engine using reader preferences  
