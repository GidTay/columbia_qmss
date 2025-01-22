Web Scraping with Selectors
===================================================================

This exercise focuses on extracting data for S&P 500 companies from individual company pages on Wikipedia, with an emphasis on data consistency and error handling.

Wikipedia does have an API. For this exercise, we will pretend there is no API and simply read-in the HTML.

### 1. Create a Function to Scrape Company Infoboxes

We’ll start by building a function to gather information from each company's individual Wikipedia page. Choose a single company to begin, such as "[Apple Inc.](https://en.wikipedia.org/wiki/Apple_Inc.)." This page contains an infobox with information like CEO, revenue, and number of employees, which we want to extract.

a) Write a function called `get_company_info` which:
   - Takes a company’s Wikipedia URL as input.
   - Extracts the following fields from the infobox:
     - **Company Name**
     - **Industry**
     - **Revenue** (normalized to billions of USD if available)
     - **Net Income** (normalized to billions of USD if available)
     - **Number of Employees**
     - **Market Cap** (normalized to billions of USD if available)
   - Handles variability in field names if necessary. 
   - Make sure to handle exceptions gracefully.
   - Returns a dictionary with these fields as keys and the extracted data as values. If a field is missing, the function should return `None` for that entry.
   
Test `get_company_info` with the Apple Inc. page to verify it works and manages exceptions gracefully.

b) Expand the function to gather information on key people in the company. Specifically, add the following fields:
   - **CEO**
   - **Founder(s)**
   - **Founded** (year)

Make sure you parse the HTML for the `Founder(s)` field to get the actual names as a comma separated string. For the CEO, parse the HTML for the key people section and identify the CEO. Add these fields to the dictionary returned by the function.

Test the function with the Apple Inc. page to verify it works and manages exceptions gracefully.

### 2. Retrieve S&P 500 Table

Navigate to the Wikipedia page with the full list of S&P 500 companies: [List of S&P 500 companies](https://en.wikipedia.org/wiki/List_of_S%26P_500_companies). This page contains a table with general information about each company.

a) Write code to scrape this table and create a `pandas` DataFrame with the following columns:
   - **Company Name**
   - **Link to Company Wikipedia page**
   - **GICS Sector**
   - **GICS Sub-Industry**
   - **Headquarters Location**
   
Display the first five rows of the DataFrame.

### 3. Add Detailed Information to the S&P 500 DataFrame

Using the `get_company_info` function you created, retrieve additional data for each company in the list:

a) Loop through each company in the DataFrame from the previous step, accessing its individual Wikipedia page to get the detailed infobox data, and add it as new columns to your main DataFrame. Once complete, export your updated DataFrame with the additional columns to a CSV.

### Submission
----------

Submit your completed assignment according to the submission instructions provided [here](/Exercises/homework_submission_instructions.md) by Wednesday, November 13 at 5pm. Ensure your submission includes:

- A jupyter notebook with code and suggested outputs.
- The CSV file with the collected data.