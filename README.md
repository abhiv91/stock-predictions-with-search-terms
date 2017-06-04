<img src="https://github.com/khyatiparekh/Data515_FinalProject/blob/master/logo.png" width="80">

# Searching For Success - Stock Investing for Dummies
## 

Searching For Success is a template project that help amateur investor to visualize search trends 
on Google for selected company and get probability that the stock price will increase when 
the quarterly reports will be released for the same company.

To use it as a template for your own project, you will need to clone this
repository into your computer and follow the instructions at the [bottom of this page]

First, let me explain all the different moving parts that make up the
python project, and all the elements which allow us to effectively
share it with others, test it, document it, and track its evolution.

### Organization of the  project

The project has the following structure:  
   * project_name/  
     * |- README.md  
     * |- LICENSE  
     * |- project_name/  
        * |- __init__.py  
        * |- project_name.py  
        * |- submodule/  
        * |- tests/  
           * |- __init__.py  
           * |- test_core.py  
        * |- setup.py   
      * |- doc/  
      * |- examples/  
           * |- demo.ipynb  
      * .gitignore  
     
In the following sections we will examine these elements one by one. First,
let's consider the core of the project. This is the code inside of
`EarningReport.py, PredictionStockPrice.py and HistoricalPlot.py`. 

### EarningReport.py

This module implements the functions: 

1) get_quarter_begin, 
2) get_quarter_end,
3) get_current_quarter_dates, 
4) print_last_day_quarter, 
5) get_default_report_dates, 
6) get_yahoo, and 
7) get_earnings_data.

The get_quarter_begin function calculates the first day of the current quarter.

The get_quarter_end function calculates the last day of the current quarter.

The get_current_quarter_dates returns the formatted begin and end dates.

The get_earnings_data first calls get_yahoo and if no earnings date, then calls get_default_report_dates for the estimated earnings report dates.

The get_yahoofunction will download stock price data from Yahoo finance, saves the daily quote information and returns the earnings report date(s).

### PredictionStockPrice.py

This module implements three functions: 
1) feature_selection,
2) prediction_model and, 
3) prediction_stock_price. 

The first function,
features_selection will use Lasso regression model to select
6 keywords that are significant to the company's stock performance.
And the second function predcition_model will predict the
likelihood of stock prices increase or decrease after upcomming
earning report released for given company. And the third function
prediction _stock_price will call the previous functions
based on the company name input.

### HistoricalDataPlot.py

This module implements one function: historical_data_plot.

The function will read the data for the input company with selected keywords and then plot Google trends for selected keywords from previous feature selection. 
Then plot daily adjusted close stock price for given company.