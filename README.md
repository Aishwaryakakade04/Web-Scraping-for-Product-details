
# Web Scraping with Python

## Overview

This repository contains Python code for web scraping using `requests` and `BeautifulSoup`. The code demonstrates how to extract data from the Flipkart homepage, including HTML tags and images.

## Prerequisites

Before running the code, make sure you have the following Python packages installed:

- `pandas`
- `requests`
- `beautifulsoup4`

You can install these packages using pip:

bash
pip install pandas requests beautifulsoup4


## Code Description

### 1. Importing Libraries

python
import pandas as pd
import requests as rcq
from bs4 import BeautifulSoup


### 2. Fetching Web Page

The following code retrieves the HTML content of the Flipkart homepage:

python
web = requests.get("https://www.flipkart.com/")
print(web)


### 3. Inspecting the Web Page

Check the URL and status code of the response:

python
web.url
web.status_code


### 4. Parsing HTML with BeautifulSoup

Parse the HTML content and extract the title, anchor tags, and header tags:

python
soup = BeautifulSoup(web.content, "html.parser")
print(soup.title)
print(soup.a)
print(soup.h1)


### 5. Extracting Images

Find and list all image tags on the page:

python
img = soup.find_all("img")


### 6. Extracting Links and Href Attributes

Extract all `href` attributes from anchor tags:

python
links = soup.find_all('a')
for link in links:
    print(link.get('href'))


### 7. Extracting Header Tags

Find and list all `h1` tags:

python
headers = soup.find_all('h1')
for header in headers:
    print(header.text)


## Notes

- Ensure that you have internet access to fetch data from Flipkart's website.
- Be mindful of the website’s `robots.txt` file and scraping policies.
- The structure of the webpage may change over time, which could affect the scraping results.


## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Contact

For any issues or inquiries, please contact [yourname](aishwarya04kakade@gmail.com).

---
