# E-Commerce Web Scraping & Book Analysis using Selenium

## 📌 Project Overview

This project demonstrates an end-to-end web scraping and data analysis workflow using Python and Selenium.

The project was developed as a practical exercise to learn browser automation, web element extraction, pagination handling, data collection, data cleaning and exploratory data analysis.

The data was collected from the **Books to Scrape** sandbox website, which is designed for practicing web scraping.

A total of **1,000 book records** were scraped using Selenium and analyzed using Pandas, Matplotlib and Seaborn.

---

## 🎯 Project Objectives

The main objectives of this project were:

- Learn web scraping using Selenium
- Locate and extract data from HTML elements
- Handle multi-page website pagination
- Use explicit waits with Selenium
- Store scraped data in a Pandas DataFrame
- Clean and transform scraped data
- Perform basic exploratory data analysis
- Create meaningful data visualizations
- Generate business-oriented observations and insights

---

## 🛠️ Technologies Used

- Python
- Selenium
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 🌐 Data Source

**Books to Scrape – Sandbox**

The website is designed specifically for practicing web scraping and provides a safe environment for learning scraping techniques.

---

## 📊 Data Collected

The scraping process collected the following information for each book:

| Column | Description |
|---|---|
| Title | Name of the book |
| Price | Book price in GBP (£) |
| Rating | Book rating from 1 to 5 |
| Availability | Availability status of the book |

### Dataset Size

- **Total Records:** 1,000
- **Total Features:** 4
- **Pages Scraped:** 50
- **Records per Page:** 20

---

## 🔄 Web Scraping Workflow

The scraping process followed these steps:

1. Opened the website using Selenium WebDriver
2. Located book elements using CSS selectors
3. Extracted title, price, rating and availability
4. Stored each book as a Python dictionary
5. Appended records into a list
6. Used Selenium pagination to navigate through all pages
7. Used `WebDriverWait` to handle page loading
8. Converted the scraped records into a Pandas DataFrame
9. Exported the final dataset as a CSV file

### Pagination Logic

The scraper automatically checked whether a **Next** button was available.

If the button existed, Selenium moved to the next page.

If no Next button was found, the scraping loop stopped.

This allowed the scraper to collect data across the complete catalog instead of scraping only the first page.

---

## 🧹 Data Cleaning

The scraped data required basic cleaning before analysis.

### Price Cleaning

The currency symbol was removed and the price was converted from text to numeric format.

Example:

`£51.77 → 51.77`

### Rating Cleaning

The scraped rating values were converted from text categories into numeric ratings.

Example:

`One → 1`

`Two → 2`

`Three → 3`

`Four → 4`

`Five → 5`

### Availability

Availability information was cleaned and retained as a categorical field.

---

## 📈 Exploratory Data Analysis

The following analyses were performed:

### 1. Book Price Distribution

The distribution of book prices was analyzed using a histogram with KDE.

**Key Findings:**

- Average book price: **£35.07**
- Minimum book price: **£10.00**
- Maximum book price: **£59.99**
- Prices are spread across a wide range rather than being concentrated around one specific price point.

**Business Insight:**

The wide price range indicates that the catalog contains books across different price segments, supporting a diverse pricing strategy for different customer groups.

---

### 2. Book Rating Distribution

The distribution of ratings from 1 to 5 was analyzed.

**Key Findings:**

- 1-star books: **226**
- 2-star books: **196**
- 3-star books: **203**
- 4-star books: **179**
- 5-star books: **196**

The rating distribution is relatively balanced across the five rating levels.

**Business Insight:**

The catalog contains books with varying levels of customer appeal rather than being dominated by highly rated books. Higher-rated books can potentially be used for recommendations and promotional activities.

---

### 3. Top 10 Most Expensive Books

The 10 highest-priced books were identified and visualized using a horizontal bar chart.

**Key Findings:**

- The most expensive book is **The Perfect Play (Play by Play #1)** at **£59.99**.
- The Top 10 books fall within a narrow price range of approximately **£59.45–£59.99**.

**Business Insight:**

The concentration of prices around £60 indicates a premium pricing range among the most expensive books. These books can be considered premium offerings when evaluating pricing and merchandising strategies.

---

## 📊 Visualizations

The project includes the following visualizations:

- Distribution of Book Prices
- Distribution of Book Ratings
- Top 10 Most Expensive Books

The visualizations were created using **Matplotlib and Seaborn**.

---

## 📁 Project Structure

```text
ecommerce-web-scraping-selenium/
│
├── Data/
│   └── books_selenium_scraped.csv
│
├── Notebook/
│   └── Selenium_Practice.ipynb
│
├── Screenshots/
│   ├── price_distribution.png
│   ├── rating_distribution.png
│   └── top_10_expensive_books.png
│
├── README.md
├── requirements.txt
└── .gitignore
