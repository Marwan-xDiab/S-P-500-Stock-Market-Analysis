# Architect and Explore a DWH for Stock Market Analysis Project.
## Data Analytics and Visualization Track 
## Table of contents
* [General info](#general-info)
* [Introduction](#Introduction)
* [Business Requirememts](#Business-Requirememts)
* [Data Sources](#Data-Sources)
* [Data Warehouse/Data Model](#Data-Model)
* [Business Queries](#Business-Queries)
* [Dashboards](#Dashboard)
* [Conclusion](#Conclusion)

* [Dashboard Link ](https://www.novypro.com/project/--sp500-dashboard-1) <br />
* [S&P 500 Stocks (Web Scraping) Link](https://www.kaggle.com/code/marwandiab/s-p-500-stocks-web-scraping) <br />
* [Report Link](https://www.novypro.com/project/--tesla-report) <br />

## General Info
This project aims to apply the theories, methodologies and strategies tackled in the training to successfully implement a data warehouse to support business intelligence queries

## Introduction
About Project Info
* S&P 500 index tracks the stock performance of 500 large companies listed on exchanges in the United States
* 36.7 trillion USD
* free-float weighted
* The index is one of the factors in the computation of the Conference Board Leading Economic Index, used to forecast the direction of the economy

## Business Requirememts
* Reporting stock market daily statistics.
* Reporting top and lowest performers.
* Tracking stock market changes.

## Data Sources
* [Wikipedia List of S&P 500 companies](https://en.wikipedia.org/wiki/List_of_S%26P_500_companies) <br />
> * <ins>Date of creation</ins>: 4 April 2022 <br />
> * <ins>Descriptions</ins>: <br />
The S&P 500 stock market index is maintained by S&P Dow Jones Indices. It comprises 503 common stocks which are issued by 500 large-cap companies traded on American stock exchanges (including the 30 companies that compose the Dow Jones Industrial Average). The index includes about 80 percent of the American equity market by capitalization. It is weighted by free-float market capitalization, so more valuable companies account for relatively more weight in the index. The index constituents and the constituent weights are updated regularly using rules published by S&P Dow Jones Indices.<br />
> * <ins>ETL</ins>: <br />
web scraping using beautiful soup and request library with python, file type (CSV) <br />
* [Yahoo finance](https://www.kaggle.com/code/marwandiab/s-p-500-stocks-web-scraping)
> * <ins>Date of creation</ins>: 1 July 2018 <br />
> * <ins>Descriptions</ins>: <br />
Yahoo Finance used to have their own official API, but this was decommissioned on May 15th 2017, following wide-spread misuse of data.
These days a range of unofficial APIs and libraries exist to access the same data, including of course yfinance.
Note you might know of yfinance under it’s old name- fix-yahoo-finance, since it was re-named on May 26th 2019 at the same time that it went over a large overhaul to fix some usability issues.<br />
> * <ins>ETL</ins>: <br />
Extract data using web scraping then imported, integrated and transferred it using SSMS, then create the model. 
* [Kaggle](https://www.kaggle.com/code/marwandiab/s-p-500-stocks-web-scraping)
> * <ins>Date of creation</ins>: 1 June 2018 <br />
> * <ins>Descriptions</ins>: <br />
The folder individual stocks 5yr contains files of data for individual stocks, labelled by their stock ticker name. The allstocks5yr.csv contains the same data, presented in a merged .csv file. Depending on the intended use (graphing, modelling, etc.) the user may prefer one of these given formats..<br />
> * <ins>ETL</ins>: <br />
Extract data using web scraping then imported, integrated and transferred it using SSMS, then create the model.<br />
## Data Warehouse/Data Model
> * <ins>Why did we choose “galaxy schema”?</ins> <br />
We used **galaxy schema** in our model due to its advantages which allowing Dimension Tables to be linked to other Dimension tables, including the Dimension Tables in the first level. This Multidimensional nature makes it easy to implement on complex Relational Database systems, thus resulting in effective Analysis & Reporting processes. <br />
> * <ins>Dimensional Model</ins> <br />
Here's our Dimensional Model Screenshot from SSMS.
![Galaxy Schema](https://user-images.githubusercontent.com/90741989/182256849-9e262cd2-402d-4ca4-bc3a-98dc9cbcc3d1.jpg)

## Business Queries 
> * Retrieve Stock performance over7 and 30 days and what are previous and current changes.
Here's Snapshoot of our Sql Query from SSMS.
![1](https://user-images.githubusercontent.com/90741989/182256909-b9aeba62-22a7-4e2b-8b07-65a2276797bf.jpg)

> * Retrieve top 10 days and worst 10 days’ changes.
Here's Snapshoot of our Sql Query from SSMS.
![2](https://user-images.githubusercontent.com/90741989/182256919-bbe978ed-e949-4c98-ae0a-13b185c01cf9.jpg)

> * Retrieve Stock performance over 7 and 30 days And previous and current changes for the symbol.
Here's Snapshoot of our Sql Query from SSMS.
![3](https://user-images.githubusercontent.com/90741989/182256934-c8dc8fcf-b162-42dc-930b-0e7f82227924.jpg)

> * Retrieve volatility KPIS per(years/week) for sectors.
Here's Snapshoot of our Sql Query from SSMS.
![4](https://user-images.githubusercontent.com/90741989/182256941-01a8ea1e-2bb8-4659-87ed-b1c4f8010c01.jpg)

> * Calculate weight of each company in the stock market.
Here's Snapshoot of our Sql Query from SSMS.
![5](https://user-images.githubusercontent.com/90741989/182256952-b2c634b3-2a3f-4224-824a-fdc1714977e9.jpg)


 ## Dashboards
> * S&P 500 <br />
Average Volume  - 10 Days top & Worst Close Change  - Performance  - volatility KPIs per secotr <br />
Here's Snapshoot of our first dashboard from PowerBI.
![D1](https://user-images.githubusercontent.com/90741989/182256962-1b9ac1bf-b8b4-4c93-a18e-41eaedb65b5e.jpg)

> * Company Monitoring <br />
Average Volume  - Historic Data  - Performance  - General Info - Filtration Page <br />
Here's Snapshoot of our first dashboard from PowerBI.
![D2](https://user-images.githubusercontent.com/90741989/182256974-449e4ad5-08f1-4b4f-98e8-cf7bb002122e.jpg)

> * Comparison <br />
Average price per month  - Top 10 loss / gain close change per company  - Company Close price per date <br />
Here's Snapshoot of our first dashboard from PowerBI.
![D3](https://user-images.githubusercontent.com/90741989/182256978-88eece3a-7183-4cd7-8273-4ce46d0361db.jpg)

> * Tesla Report <br />
Close price and volume per date  - Stock Performance KPIs  - Tesla Stock Surges - Tesla After Twitter <br />
Here's Snapshoot of our first dashboard from PowerBI. <br />
![Tesla](https://user-images.githubusercontent.com/90741989/182256993-e22aa511-a535-402b-a3c7-c6bebcea9e8e.jpg)


## Conclusion
> * Successfully visualized records from 5 years.
> * Enable Individual Company monitoring.
> * Enable Comparison of companies with ease of filtering.
> * Tesla example: Report Created.
