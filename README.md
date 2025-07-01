# 📚 Goodreads Book Scraper Project

---

## 🔎 Overview

This project implements a **web scraper** to collect detailed metadata from the Goodreads **"Best Books Ever"** list. Using Python and powerful libraries like **Requests** and **BeautifulSoup**, the scraper extracts rich book info including:

- 📖 Title & Author  
- 📝 Description  
- 📚 Genres  
- 📅 Publication data  
- ⭐ Ratings  
- 📖 Series details  

The output is a clean, structured dataset saved as a **CSV file**, ready for your data analysis and visualization adventures!

---

## 🚀 Current Functionality

- 🌐 Scrapes multiple Goodreads list pages to gather individual book URLs  
- 🔍 Visits each book’s page and extracts comprehensive metadata  
- 🔄 Handles network errors gracefully with retry logic for robustness  
- 🧩 Organizes data with Python **dataclasses** for clarity and easy transformation  
- 💾 Saves aggregated data into a well-structured CSV (`goodreads-books-raw.csv`)  

---

## 🔮 Planned Enhancements

This project is just getting started! Upcoming phases include:

- 📊 **Exploratory Data Analysis (EDA):** Statistical summaries, distributions, and pattern discovery  
- 🧹 **Data Cleaning:** Handling missing values, correcting inconsistencies, and enriching data  
- 📈 **Data Analysis & Visualization:** Creating insightful charts and dashboards about books, authors, genres, and reader engagement  
- 🤖 **Advanced Analytics:** Applying NLP on book descriptions and sentiment analysis on reviews  

---

## 🛠️ Technologies Used

- Python 3.x  
- Requests  
- BeautifulSoup4  
- Pandas & NumPy  
- Dataclasses  
- Logging  
- Jupyter Notebook  

---

## ⚙️ Usage

1. Clone the repository  
2. Install dependencies from `requirements.txt`  
3. Run the Jupyter Notebook to execute the scraper and generate the dataset  
4. Use the generated CSV file for your analysis and visualization projects  

---

## ⚠️ Notes

- Uses a custom **User-Agent** and polite scraping delays to avoid IP blocks  
- The dataset CSV is overwritten on each run to keep data fresh  

---


Thanks for checking out the project! Happy scraping and exploring! 📚✨