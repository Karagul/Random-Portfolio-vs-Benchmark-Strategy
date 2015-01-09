# Random Portfolio Generation vs Benchmark Strategy

## Overview

Building on the popular quote from the book "A Random Walk Down Wall Street" by economist Burton Malkiel that, as explained [here](http://www.automaticfinances.com/monkey-stock-picking/):

> "a blindfolded monkey throwing darts at a newspaper's financial pages could select a portfolio that would do just as well as one carefully selected by experts."

I set out to see if a randomly generated portfolio could beat a benchmark index.

This Python project models the performance of randomly generated portfolios and plots them against a benchmark. The aim is to visualise if randomly picked portfolios with the same number of constituent stocks as the benchmark index can outperform the benchmark itself.

To rather than just having a singular comparison at a time, my strategy allows for generation of an arbitrary number of random portfolios, all consisting of a specified number of equally weighted constituents, hence turning the experiment into a Monte Carlo Simulation which then gets plotted on a single graph using the [matplotlib](http://matplotlib.org/) library.

## Technical Info

* The list of stocks to randomly pick from for a portfolio is contained under _./data/_ and consists of a comma delimited file with the first column containing the Yahoo Finance ticker symbol and the second containing the company name.

* The program uses the [Yahoo Finance](https://finance.yahoo.com/) historical prices download link to fetch CSV files of the historical prices of each stock. As some stocks don't have historical prices, or contain limited history, the program deals with this by calling the _fetch\_prices(ticker)_ function recursively with another random stock until it finds one which matches the requested price history.

* The randomly generated portfolios are outputted to a comma delimited file called _rand\_portfolios.csv_ which lists the Yahoo Finance tickers of the constituents of each portfolio.

## Example Output
![Example Matplotlib Output](http://www.jakob-aungiers.com/misc/example_run_graph_output.png)