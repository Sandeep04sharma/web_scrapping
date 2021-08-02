# web_scrapping
This is simple  implementation of web scrapping  using python and store data on Sqlite3 database.

## Steps:
1. Importing libraries:
```
from bs4 import BeautifulSoup
from msedge.selenium_tools import Edge, EdgeOptions
import requests
import sqlite3
import pandas as pd
import time
import csv
import json

```
2. Defining driver and making connection with database
```
options=EdgeOptions()
options.use_chromium=True
driver= Edge(options=options)


base_url='https://www.ajio.com'
headers={'User-Agent':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.107 Safari/537.36 Edg/92.0.902.55'}
driver.get(base_url)

conn=sqlite3.connect('GroomProducts.db')
c=conn.cursor()
# c.execute('''CREATE TABLE ProductList(Website TEXT, ProductLink TEXT,ProductName TEXT, 
#            ProductBrand TEXT, ProductCat TEXT, Sizes,Price INTEGER,MRP INTEGER, Gender TEXT,Description TEXT, PrimImgLink TEXT, SecImgLinks)''')

```
3. Getting links of indivisual products from the given search item category.
4. Storing data to Sqlite3 database
5. Close the connection with database.
