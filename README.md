# Financial Planner
This program creates two financial planner tools. First, is a financial planner for emergencies. Users will use this to vizualize their current savings and also determine if they have enough reserves for an emergency fund. Second, is a financial planner for retirement. Users will use this to forecast the performance of their retirement portfolio in 30 years using a Monte Carlo simulation.

----

## Technologies
This application is written in Jupyter Lab Notebook in the Python programming language. The Python libraries, tools, and modules used in this application are Pandas, OS, Requests, JSON, dotenv, MCForecastTools, Matoplotlib, and Alpaca Trade API. Documentation shown below:

[Pandas](https://pandas.pydata.org/docs/index.html), [OS](https://docs.python.org/3/library/os.html), [Requests](https://docs.python-requests.org/en/latest/), [JSON](https://docs.python.org/3/library/json.html), [dotenv](https://pypi.org/project/python-dotenv/), [MCForecastTools](https://pypi.org/project/forecast-tools/), [Matplotlib](https://matplotlib.org/stable/index.html), [Alpaca Trade API](https://alpaca.markets/docs/trading/)

----

## Installation Guide
This program uses the Pandas library. If the user is not already running an environment that includes Pandas, then they will need to intall the library. Instructions shown in the installation guide --> [Pandas Installation Guide](https://pandas.pydata.org/docs/getting_started/install.html)

In addition, this program will require the OS module and the Requests, JSON, and dotenv libraries to facilitate API requests. 

The OS module is standard utility and does not require a special download. 

The Requests and JSON libraries should automatically be installed with the Anaconda environment. To confirm their installation, run the following code in the conda dev environment:

> conda list requests

> conda list json

The result should show both requests and json to be installed. If not, they can be installed by running the following code in the conda dev environment:

> conda install -c anaconda requests

> conda install -c jmcmurray json

To interact with APIs, the user must set up dotenv and an SDK. To install these tools, run the following code in your base terminal:

> pip install python-dotenv

> pip install alpaca-trade-api

You can verify the installations by runnning:

> pip list | grep -E "python-dotenv|alpaca-trade-api"


This program also requires API keys from Alpaca. If the user does not already have Alpaca credentials, they can obtain them by following the instructions below.

1. Create a free account on the [Alpaca website](https://app.alpaca.markets/signup) by entering an email address and a 12-character password.

2. Verify the account through email address.

3. On the "Welcome to Alpaca" page, click the "Go to Paper Account" link.

4. On the Paper Trading page, navigate to the right side to find "Your API Keys".

5. Click "Generate API Keys".

6. Copy both keys and secretly store them on your computer.

----

## Usage
For the program to run correctly, the user must make sure that all libraries and modules are correctly imported in the beginning of the code. This looks like:

    import os

    import requests

    import json

    import pandas as pd

    from dotenv import load_dotenv

    import alpaca_trade_api as tradeapi
   
    from MCForecastTools import MCSimulation

    %matplotlib inline

The user must also make sure that they have the correct API keys in their .env file. The file should be named nothing other than .env to ensure the security of their API keys. The .env file should also be in the working directory.

**The program is comprised of 2 main parts:**

1. Financial Planner for Emergencies

This section will determine the current value of a member's crypto wallet. The current prices for BTC and ETH will be collected by using the Python Requests library. The next section will determine the current value of the member's stock and bond holdings. The program will make an API call to Alpaca via the Alpaca SDK to get the current closing prices of the SPDR S&P 500 ETF Trust (ticker: SPY) and of the iShares Core US Aggregate Bond ETF (ticker: AGG). The following section will use the valuations for the crypto wallet and the stock and bond portion of the portfolio determine if the member has enough savings to build an emergency fund. 

2. Financial Planner for Retirement

This section will use the Alpaca API to get historical closing prices for a retirement portfolio. First, the program will use the MCForecastTools library to create a Monte Carlo simulation for the member's savings portfolio to forecast the performance 30 years from now. The program will also plot the results in both an overlay line plot and a histogram. The next section will adjust the portfolio to run a new Monte Carlo simulation for 10 years, to see if the member may be able to retire earlier. The program will again plot the results in an overlay line plot and a histogram.

----

## Contributors

Arlie Jones

[E-mail](arliejones98@gmail.com)  |  [LinkedIn](https://www.linkedin.com/in/arlie-jones-020092159/)

----

## License

None