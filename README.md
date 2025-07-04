# task_1
Data cleaning and preprocessing project for the Netflix Movies and TV Shows dataset using Python and Pandas. Handles missing values, duplicates, and standardizes data.

# Netflix Titles Data Cleaning Project

## 1. Project Overview

This project focuses on cleaning and preprocessing the "Netflix Movies and TV Shows" dataset. The goal is to transform raw, messy data into a clean, structured, and ready-to-use format for analysis or further modeling. Data cleaning is a crucial first step in any data science project to ensure the quality and reliability of insights.

## 2. Dataset Used

* **File Name:** <a href = 'https://github.com/Palash0321/task_1/blob/main/netflix_titles.csv'>Netflix_Movies</a>
* **Source:** This dataset typically contains information about movies and TV shows available on Netflix, including details like title, director, cast, country, release year, duration, and genres.

## 3. Tools Used

* **Python:** The programming language used for scripting.
* **Pandas Library:** A powerful Python library specifically designed for data manipulation and analysis, making data cleaning tasks efficient.
* **VSCode**

## 4. Data Cleaning Process (Step-by-Step)

Here's a breakdown of the sequential steps performed to clean the dataset:

### Step 1: Loading the Data

* **What was done:** The `netflix_titles.csv` file was loaded into a Pandas DataFrame.
* **Why:** This is the first step to get the data from the CSV file into a format that Python (and Pandas) can work with.

### Step 2: Cleaning Column Headers

* **What was done:** Column names like 'Show ID', 'Release Year' were converted to a more consistent and programming-friendly format, like `show_id`, `release_year`. This involved making all letters lowercase and replacing spaces with underscores.
* **Why:** Consistent column names make it easier to write code and prevent errors due to varying capitalization or spaces.

### Step 3: Handling Missing Values

Missing data (empty cells) can cause problems in analysis. Here's how different columns were treated:

* **'director' and 'cast' columns:**
    * **What was done:** Any missing values (empty cells) in these columns were filled with the word 'Unknown'.
    * **Why:** This ensures that every show has an entry for director and cast, even if unknown, preventing errors in later analysis and allowing us to count "Unknown" entries if needed. Importantly, existing names were *not* changed.
* **'country' column:**
    * **What was done:** Any missing values (empty cells) in these columns were filled with the word 'Unknown'.
    * **Why:** For categorical data like 'country', filling with the Unknown.
* **'date_added' column:**
    * **What was done:** Any missing values (empty cells) in these columns were filled with the word 'Unknown'.
    * **Why:** filling with the unknown.
* **'rating' column:**
    * **What was done:** Missing values were filled with the Unknown.
    * **Why:** Similar to 'country', this maintains completeness for a categorical column.
* **'duration' column:**
    * **What was done:** Any missing values were filled with 'Unknown'.
    * **Why:** Ensures no empty cells remain for duration.

### Step 4: Removing Duplicate Records

* **What was done:** The dataset was checked for any rows that were exact copies of each other, specifically looking at the `show_id` (since each show should have a unique ID). If duplicates were found, only the first occurrence was kept, and the rest were removed.
* **Why:** Duplicate records can skew analysis results, so removing them ensures each piece of information is counted only once.

### Step 5: Standardizing Text Values

This step ensures text data is consistent in its spelling and capitalization.

* **'type' column:**
    * **What was done:** All entries were converted to lowercase (e.g., 'Movie' became 'movie').
    * **Why:** Guarantees consistency when filtering or grouping by 'type'.
* **'listed_in' (genres) column:**
    * **What was done:** Each genre within the string (e.g., "Documentaries, Reality TV") was cleaned by removing extra spaces and capitalizing the first letter of each word (e.g., "Documentaries, Reality Tv").
    * **Why:** Improves readability and ensures consistent genre categorization.
* **'director', 'cast', 'country', 'rating' columns:**
    * **What was done:** All text entries in these columns had extra spaces removed from their start/end, and were converted to Title Case (first letter of each word capitalized, e.g., 'united states' became 'United States').
    * **Why:** Creates a uniform appearance for names and categories, reducing inconsistencies.

### Step 6: Checking and Fixing Data Types

* **What was done:** The `release_year` column was explicitly converted to an integer (whole number) type.
* **Why:** `release_year` represents a year and should be stored as a whole number for correct interpretation and potential numerical operations. This step ensures the data type is appropriate.


## 5. How to Run This Project

1.  **Prerequisites:** Make sure you have Python and the Pandas library installed.
2.  **Files:** Place the file `task-1.ipynb` if you prefer Jupyter Notebook) and `netflix_titles.csv` files in the same directory.
3.  **Run:**
    * **For Jupyter Notebook (`.ipynb`):** Open the notebook in Jupyter (or VS Code with Jupyter extension) and run all the cells.

## 6. Conclusion

By following these steps, the raw Netflix dataset has been successfully transformed into a clean, consistent, and well-structured format. This refined dataset is now ready for in-depth data analysis, allowing for more accurate insights and reliable conclusions about Netflix content.
