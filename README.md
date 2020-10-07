# Designing an Automated Trading Strategy using Machine Learning

## about this liveProject

In this liveProject, you will be a data scientist at an investment firm like a hedge fund that runs algorithmic trading strategies. Your goal will be to design a trading strategy based on the predictions of a machine learning (ML) model for a portfolio manager who trades US equities with a daily or longer investment horizon. While the firm has deep experience in quantitative trading, it has  recently got interested in using ML. The rapid progress in ML coupled with exponentially growing availability of ever more diverse data has enabled novel approaches to quantitative investment. As a result, the demand for skilled data scientists capable of extracting signals from data using modern ML techniques that can inform a profitable trading strategy is also on the rise.

Your work will be getting a lot attention by your manager because you are going to develop the new strategy from scratch, building an end-to-end strategy workflow from sourcing market data, engineering predictive features and designing and comparing various ML models to implementing a trading strategy and backtesting its performance.
    
More specifically, your assignment will include the following steps:
1. Source financial market data containing historic price information
2. Engineer financial features based on commonly used technical indicators deemed to contain some predictive information about future returns
3. Build, tune and test an ML model to predict asset returns for a given price horizon
4. Evaluate the signal quality of the resulting model predictions using Alphalens
5. Develop a trading strategy by defining rules that translate model predictions into trades
6. Backtest the strategy using Zipline, and 
7. Evaluate the result using common performance and risk measures using pyfolio.

## Techniques employed
The following are some of the techniques you’ll employ throughout this project. Don’t worry if you haven’t mastered one of these areas; we’ll give you the resources to learn more. Data scientists must use a diverse range of techniques, many of which are picked up on the job for a specific project!

Listed under the bullets are the Python libraries for the technique.

- Setting up a local environment and sourcing data
    - `Docker`: containers that package standardized code and run across platforms 
- Engineering financial features for predictive modeling
    - `pandas`: data manipulation and analysis
    - TA-Lib: technical analysis library for python
- Training a regularized linear regression model
    - `scikit-learn`: machine learning
- Tuning a gradient boosting ML model
    - `LightGBM`:  fast framework for tree based learning algorithms
- Assessing the signal quality of ML predictions
    - `alphalens`: performance analysis of predictive (alpha) stock factors
- Analyzing algorithm output and tuning model settings to improve result
- Interpreting algorithm results in the problem domain
- Designing and backtesting a trading strategy
    - `Zipline`: algorithmic trading library for event-driven backtesting
- Evaluating the performance of the trading strategy
    - `pyfolio`: portfolio and risk analytics of financial portfolios
- Summarizing findings of a data science project effectively
    - `nbconvert`: converting Jupyter Notebooks to reports

Resources are provided for working with these techniques/libraries both as embedded in Manning liveBooks and as links to external documentation. On the job, you will often be given partial information and must learn how to seek out relevant resources on your own!

## Project outline
The project is broken into four parts.

1. Setting up your local Python environment using Docker and sourcing market data

2. Engineering predictive alpha factors from asset price data

3. Designing, tuning and evaluating the performance of ML models 

4. Building, backtesting, and evaluating a trading strategy

The skills covered in order are the following: working with docker, manipulating financial data, interpreting algorithm results, designing and evaluating a trading strategy, and producing an actionable report. The deliverable from each part is a Jupyter notebook (preferably on GitHub) documenting your workflow and results. The final milestone will be a notebook converted to html or a PDF to share the conclusions with your manager at the investment firm. Each section builds upon the previous and will test your skills in a different area of financial data science. As you go through the project, keep in mind the overall objective: to define a trading strategy that shows promising backtest results. The project is representative of problems solved by data scientists in the investment industry and utilizes very popular tools for data science in Python.

## Prerequisites
The liveProject is for intermediate Python programmers who know the basics of data science. To begin this liveProject, you will need to be familiar with:

TOOLS
- Basics of pandas
- Basics of scikit-learn
- Basics of LightGBM
- Basics of financial metrics and technical indicators
- Basics of Jupyter Notebook

An enthusiasm for solving problems and self-led learning will also prove quite useful (and not just in this project)!

## Python libraries and setup

This uses Python 3.7 (and 3.5 for the `Zipline` part). The first milestone is about setting up Anaconda environments containing the requisite libraries using a Docker image. Additional instructions will be provided.

Managing Python package versions with virtual environments is a crucial data science skill to avoid situations where code that works on one machine causes errors on another! Docker is very helpful in this regard.

## Dataset

The project uses the Quandl Wiki dataset containing over 3,000 US equities through March 2018. It is available free of charge upon registration and integrates seamlessly with the open-source backtesting engine `Zipline`.

## Recommended resources

Hands-on Machine Learning for Algorithmic Trading by Stefan Jansen
Data Science Bookcamp by Leonard Apeltsin
The Quick Python Book, Third Edition by Naomi Ceder
Think Like a Data Scientist by Brian Godsey
Documentation on Python libraries:

- [pandas](https://pandas.pydata.org/docs/)
- [alphalens](https://quantopian.github.io/alphalens/)
- [scikit-learn](https://scikit-learn.org/stable/)
- [LightGBM](https://lightgbm.readthedocs.io/en/latest/)
- [Zipline](https://www.zipline.io/)
- [pyfolio](https://quantopian.github.io/pyfolio/)
- [Quantopian](https://www.quantopian.com/)
- [Stack Overflow](https://stackoverflow.com/)
- [Jupyter documentation](https://jupyter.org/documentation)
- [Python official docs](https://docs.python.org/3/)

Additional resources and tutorials are provided throughout the project. Feel free to use any resources you can find to complete the project.
If you run into problems or have questions, refer to the Frequently Asked Questions (FAQs) within the Summary section.