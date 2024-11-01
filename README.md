# Analyzing Lagos' Historic Weather Data (January to October 2024)
![](lagos.jpg)
I personally have an interest in using Python to analyze any structured data that I can get my hands on, and thus, the reason for this project. The weather in Lagos state this year has been an interesting narration of sweltering high and shivering low temperatures (though not as low as it is in nations in the northern hemisphere). Here, I showcase my webscraping, data modelling and analytical skills to visualize patterns in the weather for the common user to understand. 
```python
try:
    !pip install html5lib
    print("html5lib installation was successful.")
except OSError:
    print("Something went wrong in the installation. Try importing {html5lib} to make sure it was successfully installed.")
try:
    !pip install bs4
    print("bs4 installation was successful.")
except OSError:
    print("Something went wrong in the installation. Try importing {BeautifulSoup} to make sure it was successfully installed.")

import warnings
warnings.filterwarnings("ignore", category=DeprecationWarning)
import html5lib
from bs4 import BeautifulSoup

import requests
import pandas as pd
print ('all libraries were installed')
```
[![Go to screenshot to view output](https://via.placeholder.com/210x25/007bff/000000?text=Go+to+screenshot+to+view+output)](libraries.png)

Sadly the code failed as it was not able to return a table due to specific reasons.
[![Go to screenshot](https://via.placeholder.com/210x25/007bff/000000?text=Go+to+screenshot+to+view+output)](html5lib_failed.png)

so I used the selenium and "time" modules instead.
```python
try:
    %pip install selenium
    print("selenium installation was successful.")
except OSError:
    print("Something went wrong in the installation. Try importing {selenium} to make sure it was successfully installed.")
from selenium import webdriver
import time
print ("selenium was successfully installed and imported")

driver = webdriver.Chrome()
url = "https://www.wunderground.com/history/monthly/ng/lagos/DNMM/date/2024-1"
driver.get(url)
time.sleep(1)
soup = BeautifulSoup(driver.page_source, 'html5lib')
table = soup.find_all('tr')
print(table)
```

