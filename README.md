# Stock Price vs News Sentiment Analysis

An end-to-end analysis exploring the relationship between stock news sentiment and stock price movements using both **FinBERT** and **VADER** sentiment models.

## Overview

This project investigates whether stock news sentiment can be used to predict stock price movements (daily, intraday, and next-day returns) across 10 major tickers. The analysis combines NLP-based sentiment scoring with time series visualization and correlation analysis.

A key discovery was that while Pearson correlations were generally weak, **Savitzky-Golay smoothed time series graphs** revealed meaningful visual patterns between sentiment and returns. The project also explores the "chicken or egg" dynamic — whether news sentiment leads prices or vice versa.

## Repository Structure

| File | Description |
|------|-------------|
| `News_DataExploration.ipynb` | Identified the top 10 tickers by news volume and discovered the dataset only covers March 2025 – March 2026 |
| `Prices_DataExploration.ipynb` | Extracted matching price data for the 10 selected tickers and time range |
| `News_Sentiment.ipynb` | Generated daily sentiment scores using both FinBERT and VADER |
| `Analysis.ipynb` | Explored relationships between sentiment and returns; determined the two main visualization approaches |
| `Savgol_Graph_Producer.ipynb` | Automated generation of 60 Savitzky-Golay smoothed time series graphs |
| `ScatterPlot_Producer.ipynb` | Automated generation of 60 scatterplot correlation graphs |
| `Appendices_Producer.ipynb` | Combined 120 generated graphs into organized appendices |
| `Stock Price 2 Sentiment Comparison - Report.pdf` | Main written report (split into parts due to GitHub file size limits) |
| `Appendix_A_Savistky_Golay_Graphs_Part1.pdf` / `Part2.pdf` | Full set of Savitzky-Golay time series visualizations |
| `Appendix_B_Correlation_Analysis.pdf` | Full set of scatterplot correlation visualizations |

## Key Findings

- Pearson correlations between sentiment and returns were consistently weak across all tickers and return types.
- **Savitzky-Golay smoothed time series** visualizations revealed clearer relationships between sentiment peaks/valleys and price movements than correlation scores alone.
- Evidence of both directions of influence (news sentiment → price movement **and** price movement → news sentiment), varying by ticker.
- FinBERT slightly outperformed VADER, but the difference was not substantial.
- The relationship between news and price appears to depend on whether a stock is more retail-driven or institutionally-driven.

## Tech Stack & Approach

- **Sentiment Analysis**: FinBERT (financial domain) + VADER
- **Data Processing**: pandas, custom aggregation to daily means
- **Visualization**: Matplotlib + Savitzky-Golay filtering for trend smoothing
- **Automation**: Built dedicated producer notebooks to efficiently generate and organize 120 graphs into appendices

## Top 10 Tickers Analyzed

AAPL, AMZN, FDS, GOOG, INTC, META, MSFT, NVDA, PLTR, TSLA

## Conclusion

This project demonstrates that simple correlation metrics can understate relationships in financial time series. Visual pattern analysis using smoothed trends provided deeper insight into the complex, bidirectional relationship between news sentiment and stock prices.
