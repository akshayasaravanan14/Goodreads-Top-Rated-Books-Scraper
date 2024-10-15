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

### Script Overview

```r
library(rvest)
library(dplyr)

# Define the URL of the Goodreads list
link <- "https://www.goodreads.com/list/show/10198.Books_With_a_Goodreads_Average_Rating_of_4_5_and_above_and_With_At_Least_100_Ratings"

# Read the webpage's HTML content
web <- read_html(link)

# Extract book titles
Name <- web %>% html_nodes(".bookTitle span") %>% html_text()

# Extract author names
Author <- web %>% html_nodes(".authorName span") %>% html_text()

# Combine the extracted data into a data frame
Booksrating <- data.frame(Name, Author)

# Save the data to a CSV file
write.csv(Booksrating, "Top Books.csv")
```

## Output

- The output is a CSV file named `Top Books.csv`, which contains two columns:
  - **Name**: The name of the book.
  - **Author**: The name of the book's author.
