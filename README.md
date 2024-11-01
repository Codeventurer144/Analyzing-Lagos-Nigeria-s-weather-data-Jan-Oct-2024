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

url = "https://www.wunderground.com/history/monthly/ng/lagos/DNMM/date/2024-1" 
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html5lib')
table = soup.find_all('table') 
table
```
[![Go to Screenshot](https://via.placeholder.com/150x50/007bff/000000?text=Go+to+Screenshot&font-weight=bold)](libraries.png)

