<h1 align="center">Web Price Search Automation</h1>
<p align="center">
  <img alt="Github top language" src="https://img.shields.io/github/languages/top/gsoaresdz/web-price-search-automation?color=56BEB8">
  <img alt="Github language count" src="https://img.shields.io/github/languages/count/gsoaresdz/web-price-search-automation?color=56BEB8">
  <img alt="Repository size" src="https://img.shields.io/github/repo-size/gsoaresdz/web-price-search-automation?color=56BEB8">
  <!--<img alt="License" src="https://img.shields.io/github/license/gsoaresdz/automacao-web-busca-de-precos?color=56BEB8">-->
</p>
<p align="center">
  <a href="#dart-about">About</a> &#xa0; | &#xa0; 
  <a href="#sparkles-features">Features</a> &#xa0; | &#xa0;
  <a href="#rocket-technologies">Technologies</a> &#xa0; | &#xa0;
  <a href="#white_check_mark-requirements">Requirements</a> &#xa0; | &#xa0;
  <a href="#checkered_flag-execution">Execution</a> &#xa0; | &#xa0;
  <a href="#memo-license">License</a> &#xa0; | &#xa0;
  <a href="https://github.com/gsoaresdz" target="_blank">Author</a>
</p>
<br>

## **:dart: About**

This project consists of a Python script that automates the process of searching for prices on the web and storing the results in an Excel file. The script uses the following libraries:

- **pandas:** for data manipulation.
- **selenium:** to control the browser and perform web searches.
- **openpyxl:** to handle Excel files.

## **:memo: IDE and Python Version**

The script was developed using Jupyter Notebook with Python version 3.8.

## **:memo: Business Rules**

The script operates as follows:

1. Imports an Excel file containing the products to be searched.
2. Opens the browser and performs searches on the specified websites.
3. Collects product prices and stores the results in an Excel file.

## **:memo: Steps Executed in the Code**

The code is divided into two main parts:

- Importing the Excel File
- Automating Price Searches

## **:memo: Importing the Excel File**

The first part of the code imports the Excel file containing the products to be searched. The file should have the following columns:

- **Product:** the name of the product.
- **URL:** the URL of the product's search page.

The code uses the pandas library to import the Excel file. The following code shows how to import the file:

```python
products_df = pd.read_excel('searches.xlsx')
```

## **:sparkles: Features**

The second part of the code automates price searches for the products listed in the Excel file. The code operates as follows:

:heavy_check_mark: **Feature 1**: Opens the browser and accesses the specified URLs.

:heavy_check_mark: **Feature 2**: Collects product prices from the accessed pages.

:heavy_check_mark: **Feature 3**: Stores the results in an Excel file.

The following code shows how to perform a search and collect the price:

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import pandas as pd

# Configure the webdriver
browser = webdriver.Chrome()

# Loop through each URL and collect the prices
for i in range(len(products_df)):
    product = products_df.loc[i, 'Product']
    url = products_df.loc[i, 'URL']
    browser.get(url)
    price = browser.find_element(By.CLASS_NAME, 'price').text  # Example of price class
    products_df.loc[i, 'Price'] = price

# Save the results to a new Excel file
products_df.to_excel('Offers.xlsx', index=False)
```

## **:rocket: Technologies**

The following tools were used in this project:

- [Python](https://www.python.org/)
- [Jupyter](https://jupyter.org/)
- [Selenium](https://www.selenium.dev/)
- [Pandas](https://pandas.pydata.org/)
- [Openpyxl](https://openpyxl.readthedocs.io/)

## **:white_check_mark: Requirements**

Before starting :checkered_flag:, ensure you have [Git](https://git-scm.com/) and [Python](https://www.python.org/) installed.

## **:checkered_flag: Execution**

```bash
# Clone the project
$ git clone https://github.com/gsoaresdz/automacao-web-busca-de-precos.git

# Navigate to the project directory
$ cd automacao-web-busca-de-precos

# Install dependencies
$ pip install -r requirements.txt

# Run the script
$ jupyter notebook main.ipynb
```

## **:memo: Notes**

- This script was developed for educational purposes. It is not recommended to use the script for commercial purposes without authorization from the websites.
- The script can be modified to meet different needs, such as changing the price class or adding new features.

## **:memo: License**

This project is under the MIT license. For more details, see the [LICENSE](LICENSE) file.

Made with :heart: by <a href="https://github.com/gsoaresdz" target="_blank">gsoaresdz</a>

<a href="#top">Back to top</a>
