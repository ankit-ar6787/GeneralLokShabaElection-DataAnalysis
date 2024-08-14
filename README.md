# LokShabaElection2024-DataAnalysis (Data Analysis via Web Scraping)


This project entails collecting and analyzing data from the recently concluded Lok Sabha elections. The data is scraped from the Election Commission of India's website and is used to generate a comprehensive report highlighting key insights. Various visualizations are created to effectively present the findings.

## Requirements

- **Python 3.x**
- **Libraries:**
  - `pandas`
  - `requests`
  - `BeautifulSoup`
  - `matplotlib`
  - `seaborn`

## Data Scraping

The election data was retrieved by scraping the Election Commission of India's website using the `requests` and `BeautifulSoup` libraries. The focus of the data extraction was on the following details:

### State-wise Voting Data:
- **State Name**
- **Parliamentary Constituency**
- **Winning Candidate**
- **Total Votes**
- **Winning Margin**
- **Party Name**

### Party-wise Performance:
- **Party Name**
- **Seats Won**
- **Seats Leading**
- **Total Seats**

### Sample Code Snippet

Below is an example of how to scrape the data:

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

url = 'https://results.eci.gov.in'
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html.parser')

# Extract data (this is a simplified example and may require adjustments based on the website's structure)
state_data = []
for option in soup.find(id='ctl00_ContentPlaceHolder1_Result1_ddlState').find_all('option'):
    state_data.append(option.text)

# Proceed with scraping the additional required details and store them in a pandas DataFrame
```

--- 

