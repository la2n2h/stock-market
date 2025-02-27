# Stock-market
a new startup investment firm that helps customers invest their money in stocks. Job is to extract financial data like historical share price and quarterly revenue reportings from various sources using Python libraries and webscraping on popular stocks. After collecting this data you will visualize it in a dashboard to identify patterns or trends. The stocks we will work with are Apple, Netfix, Tesla,, and GameStop.

### Dashboard Analytics Displayed

A dashboard often provides a view of key performance indicators in a clear way. Analyzing a data set and extracting key performance indicators will be practiced. Prompts will be used to support learning in accessing and displaying data in dashboards. Learning how to display key performance indicators on a dashboard will be included in this assignment. We will be using Plotly in this course for data visualization and is not a requirement to take this course.

### What is stock shares
A company's stock share is a piece of the company; more precisely:

A stock (also known as equity) is a security that represents the ownership of a fraction of a corporation. ThisEntitles the owner of the stock to a proportion of the corporation's asset and profits equal to how much stock they own. Units of stock are called "shares." [1]

An investor can buy a stock and sell it later. If the stock price increases, the investor profits. If it decreases, the investor will incur a loss.  Determining the stock price is complex; it depends on the number of outstanding shares, the size of the company's future profits, and much more. People trade stocks throughout the day. The stock ticker is a report of the price of a certain stock, updated continuously throughout the trading session by the various stock market exchanges. 

# PROCESS

## Apple

### install yfinance and matplotib library
```
!pip install yfinance
!pip install matplotlib
```
```
import yfinance as yf
import pandas as pd
```

### extract stock data of Apple company
create an object that will allow to access functions to extract data
```
apple = yf.Ticker('AAPL')
```
access functions and variables to extract the type of data
```
!wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0220EN-SkillsNetwork/data/apple.json
```

### extract information about the stock as a Python dictionary
```
import json
with open('apple.json') as json_file:
    apple_info=json.load(json_file)
apple_info
```
{'zip': '95014',
 'sector': 'Technology',
 'fullTimeEmployees': 100000,
 'longBusinessSummary': 'Apple Inc. designs, manufactures, and markets smartphones, personal computers, tablets, wearables, and accessories worldwide. It also sells various related services. In addition, the company offers iPhone, a line of smartphones; Mac, a line of personal computers; iPad, a line of multi-purpose tablets; AirPods Max, an over-ear wireless headphone; and wearables, home, and accessories comprising AirPods, Apple TV, Apple Watch, Beats products, HomePod, and iPod touch. Further, it provides AppleCare support services; cloud services store services; and operates various platforms, including the App Store that allow customers to discover and download applications and digital content, such as books, music, video, games, and podcasts. Additionally, the company offers various services, such as Apple Arcade, a game subscription service; Apple Music, which offers users a curated listening experience with on-demand radio stations; Apple News+, a subscription news and magazine service; Apple TV+, which offers exclusive original content; Apple Card, a co-branded credit card; and Apple Pay, a cashless payment service, as well as licenses its intellectual property. The company serves consumers, and small and mid-sized businesses; and the education, enterprise, and government markets. It distributes third-party applications for its products through the App Store. The company also sells its products through its retail and online stores, and direct sales force; and third-party cellular network carriers, wholesalers, retailers, and resellers. Apple Inc. was incorporated in 1977 and is headquartered in Cupertino, California.',
 'city': 'Cupertino',
 'phone': '408 996 1010',
 'state': 'CA',
 'country': 'United States',
 'companyOfficers': [],
 'website': 'https://www.apple.com',
 'maxAge': 1,
 'address1': 'One Apple Park Way',
 'industry': 'Consumer Electronics',
 'ebitdaMargins': 0.33890998,
 'profitMargins': 0.26579002,
 'grossMargins': 0.43019,
 'operatingCashflow': 112241000448,
 'revenueGrowth': 0.112,
 'operatingMargins': 0.309,
 'ebitda': 128217997312,
 'targetLowPrice': 160,
 'recommendationKey': 'buy',
 'grossProfits': 152836000000,
 'freeCashflow': 80153247744,
 'targetMedianPrice': 199.5,
 'currentPrice': 177.77,
 'earningsGrowth': 0.25,
 'currentRatio': 1.038,
 'returnOnAssets': 0.19875,
 'numberOfAnalystOpinions': 44,
 'targetMeanPrice': 193.53,
 'debtToEquity': 170.714,
 'returnOnEquity': 1.45567,
 'targetHighPrice': 215,
 'totalCash': 63913000960,
 'totalDebt': 122797998080,
 'totalRevenue': 378323009536,
 'totalCashPerShare': 3.916,
 'financialCurrency': 'USD',
 'revenuePerShare': 22.838,
 'quickRatio': 0.875,
 'recommendationMean': 1.8,
 'exchange': 'NMS',
 'shortName': 'Apple Inc.',
 'longName': 'Apple Inc.',
 'exchangeTimezoneName': 'America/New_York',
 'exchangeTimezoneShortName': 'EDT',
 'isEsgPopulated': False,
 'gmtOffSetMilliseconds': '-14400000',
 'quoteType': 'EQUITY',
 'symbol': 'AAPL',
 'messageBoardId': 'finmb_24937',
 'market': 'us_market',
 'annualHoldingsTurnover': None,
 'enterpriseToRevenue': 7.824,
 'beta3Year': None,
 'enterpriseToEbitda': 23.086,
 '52WeekChange': 0.4549594,
 'morningStarRiskRating': None,
 'forwardEps': 6.56,
 'revenueQuarterlyGrowth': None,
 'sharesOutstanding': 16319399936,
 'fundInceptionDate': None,
 'annualReportExpenseRatio': None,
 'totalAssets': None,
 'bookValue': 4.402,
 'sharesShort': 111286790,
 'sharesPercentSharesOut': 0.0068,
 'fundFamily': None,
 'lastFiscalYearEnd': 1632528000,
 'heldPercentInstitutions': 0.59397,
 'netIncomeToCommon': 100554997760,
 'trailingEps': 6.015,
 'lastDividendValue': 0.22,
 'SandP52WeekChange': 0.15217662,
 'priceToBook': 40.38392,
 'heldPercentInsiders': 0.0007,
 'nextFiscalYearEnd': 1695600000,
 'yield': None,
 'mostRecentQuarter': 1640390400,
 'shortRatio': 1.21,
 'sharesShortPreviousMonthDate': 1644883200,
 'floatShares': 16302795170,
 'beta': 1.185531,
 'enterpriseValue': 2959991898112,
 'priceHint': 2,
 'threeYearAverageReturn': None,
 'lastSplitDate': 1598832000,
 'lastSplitFactor': '4:1',
 'legalType': None,
 'lastDividendDate': 1643932800,
 'morningStarOverallRating': None,
 'earningsQuarterlyGrowth': 0.204,
 'priceToSalesTrailing12Months': 7.668314,
 'dateShortInterest': 1647302400,
 'pegRatio': 1.94,
 'ytdReturn': None,
 'forwardPE': 27.099087,
 'lastCapGain': None,
 'shortPercentOfFloat': 0.0068,
 'sharesShortPriorMonth': 108944701,
 'impliedSharesOutstanding': 0,
 'category': None,
 'fiveYearAverageReturn': None,
 'previousClose': 178.96,
 'regularMarketOpen': 178.55,
 'twoHundredDayAverage': 156.03505,
 'trailingAnnualDividendYield': 0.004833482,
 'payoutRatio': 0.1434,
 'volume24Hr': None,
 'regularMarketDayHigh': 179.61,
 'navPrice': None,
 'averageDailyVolume10Day': 93823630,
 'regularMarketPreviousClose': 178.96,
 'fiftyDayAverage': 166.498,
 'trailingAnnualDividendRate': 0.865,
 'open': 178.55,
 'toCurrency': None,
 'averageVolume10days': 93823630,
 'expireDate': None,
 'algorithm': None,
 'dividendRate': 0.88,
 'exDividendDate': 1643932800,
 'circulatingSupply': None,
 'startDate': None,
 'regularMarketDayLow': 176.7,
 'currency': 'USD',
 'trailingPE': 29.55445,
 'regularMarketVolume': 92633154,
 'lastMarket': None,
 'maxSupply': None,
 'openInterest': None,
 'marketCap': 2901099675648,
 'volumeAllCurrencies': None,
 'strikePrice': None,
 'averageVolume': 95342043,
 'dayLow': 176.7,
 'ask': 178.53,
 'askSize': 800,
 'volume': 92633154,
 'fiftyTwoWeekHigh': 182.94,
 'fromCurrency': None,
 'fiveYearAvgDividendYield': 1.13,
 'fiftyTwoWeekLow': 122.25,
 'bid': 178.4,
 'tradeable': False,
 'dividendYield': 0.005,
 'bidSize': 3200,
 'dayHigh': 179.61,
 'regularMarketPrice': 177.77,
 'preMarketPrice': 178.38,
 'logo_url': 'https://logo.clearbit.com/apple.com'}

 ### Extracting Share Price
 ```
apple_share_price_data = apple.history(period="max")
apple_share_price_data.head()
```
| Open                      | High     | Low      | Close    | Volume   | Dividends | Stock Splits |
|---------------------------|----------|----------|----------|----------|-----------|--------------|
| Date                      |          |          |          |          |           |              |     |
| 1980-12-12 00:00:00-05:00 | 0.098726 | 0.099155 | 0.098726 | 0.098726 | 469033600 | 0.0          | 0.0 |
| 1980-12-15 00:00:00-05:00 | 0.094005 | 0.094005 | 0.093575 | 0.093575 | 175884800 | 0.0          | 0.0 |
| 1980-12-16 00:00:00-05:00 | 0.087136 | 0.087136 | 0.086707 | 0.086707 | 105728000 | 0.0          | 0.0 |
| 1980-12-17 00:00:00-05:00 | 0.088853 | 0.089282 | 0.088853 | 0.088853 | 86441600  | 0.0          | 0.0 |
| 1980-12-18 00:00:00-05:00 | 0.091429 | 0.091858 | 0.091429 | 0.091429 | 73449600  | 0.0          | 0.0 |


reset the index of the DataFrame with the reset_index function. We also set the inplace paramter to True so the change takes place to the DataFrame itself.
```
apple_share_price_data.reset_index(inplace=True)
```

plot the Open price against the Date:
```
apple_share_price_data.plot(x='Date', y='Open')
```

![download](https://github.com/user-attachments/assets/ee15a21e-bef0-4919-8391-2dc7af468bbf)

### Extracting Dividends
Dividends are the distribution of a companys profits to shareholders. In this case they are defined as an amount of money returned per share an investor owns. Using the variable dividends we can get a dataframe of the data. The period of the data is given by the period defined in the 'history` function.
```
apple.dividends
```
| Date                                        |
|---------------------------------------------|
| 1987-05-11 00:00:00-04:00    0.000536       |
| 1987-08-10 00:00:00-04:00    0.000536       |
| 1987-11-17 00:00:00-05:00    0.000714       |
| 1988-02-12 00:00:00-05:00    0.000714       |
| 1988-05-16 00:00:00-04:00    0.000714       |
|                                ...          |
| 2024-02-09 00:00:00-05:00    0.240000       |
| 2024-05-10 00:00:00-04:00    0.250000       |
| 2024-08-12 00:00:00-04:00    0.250000       |
| 2024-11-08 00:00:00-05:00    0.250000       |
| 2025-02-10 00:00:00-05:00    0.250000       |
| Name: Dividends, Length: 86, dtype: float64 |

plot the dividends overtime
```
apple.dividents.plot(0
```
![download](https://github.com/user-attachments/assets/3b4bd8d5-9f26-4053-af50-b3dca86b9408)

## Netfix
import library
```
!pip install pandas
!pip install requests
!pip install bs4
!pip install html5lib 
!pip install lxml
!pip install plotly
```
```
import pandas as pd
import requests
from bs4 import BeautifulSoup as bs
```
```
import warnings
# Ignore all warnings
warnings.filterwarnings("ignore", category=FutureWarning)
```


### Send an HTTP request to the web page
```
url = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0220EN-SkillsNetwork/labs/project/netflix_data_webpage.html"
data = requests.get(url).text
print(data)
```

### Parse the HTML content
create a new BeautifulSoup object
```
soup = bs(data,'html.parser')
```

### crape the content of the HTML web page and convert the table into a data frame.

```
netflix_data=pd.DataFrame(columns = ['Date', 'Open', 'High', 'Low', 'Close', 'Adj Close', 'Volume'])
data_list = []
for row in soup.find('tbody').find_all('tr'):
    col = row.find_all('td')
    date = col[0].text
    Open = col[1].text
    high = col[2].text
    low = col[3].text
    close = col[4].text
    adj_close = col[5].text
    volume = col[6].text
    data_list.append([date , Open, high, low, close, adj_close, volume])
netflix_data=pd.DataFrame(data_list, columns = ['Date', 'Open', 'High', 'Low', 'Close', 'Adj Close', 'Volume'])
```
print out the data frame
```
netflix_data.head()
```
| Date | Open         | High   | Low    | Close  | Adj Close | Volume |
|------|--------------|--------|--------|--------|-----------|--------|
| 0    | Jun 01, 2021 | 504.01 | 536.13 | 482.14 | 528.21    | 528.21 | 78,560,600  |
| 1    | May 01, 2021 | 512.65 | 518.95 | 478.54 | 502.81    | 502.81 | 66,927,600  |
| 2    | Apr 01, 2021 | 529.93 | 563.56 | 499.00 | 513.47    | 513.47 | 111,573,300 |
| 3    | Mar 01, 2021 | 545.57 | 556.99 | 492.85 | 521.66    | 521.66 | 90,183,900  |
| 4    | Feb 01, 2021 | 536.79 | 566.65 | 518.28 | 538.85    | 538.85 | 61,902,300  |




