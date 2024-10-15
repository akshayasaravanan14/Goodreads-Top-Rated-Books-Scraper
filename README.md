# Goodreads Top Rated Books Scraper

This repository contains an R script that scrapes book titles and author names from a Goodreads list of books with an average rating of 4.5 and above and at least 100 ratings. The script extracts the book details using web scraping techniques and saves the data to a CSV file.

## Features

- Extracts book names and authors from a Goodreads webpage.
- Saves the scraped data in a CSV file named `Top Books.csv`.

## Prerequisites

To run this script, you need to have R installed, along with the following R packages:

- `rvest`: For web scraping.
- `dplyr`: For data manipulation.

You can install the necessary packages using the following commands:

```r
install.packages("rvest")
install.packages("dplyr")
```

## How to Use

1. Clone or download this repository.
2. Open the R script in your R environment (e.g., RStudio).
3. Run the script. It will:
   - Scrape the Goodreads webpage.
   - Extract book titles and their corresponding authors.
   - Save the data to a CSV file named `Top Books.csv`.

### Code Explanation

- The script starts by loading the `rvest` and `dplyr` libraries.
- It reads the HTML content from the Goodreads webpage and extracts:
  - Book titles using the CSS selector `.bookTitle span`.
  - Author names using the CSS selector `.authorName span`.
- The extracted data is stored in a data frame and then exported to a CSV file.


## Output

- The output is a CSV file named `Top Books.csv`, which contains two columns:
  - **Name**: The name of the book.
  - **Author**: The name of the book's author.
