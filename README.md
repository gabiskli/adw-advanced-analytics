# Introduction

This repository is part of the development of the final project of the Indicium Lighthouse Program. The project involved using Adventure Works databased to create a Data Warehouse of sales information to help business stakeholders make better informed decisions. After creating de DW and modeling the data, the final star schema model was used to created a dashboard used by operational team and a relatory to the CEO. The final step of the project involved using the data modeled to predict sales demand as a POC to the planning team of ADW.

Here we have the advandced analytics part of the projects, which includes both dashboard and sales prediction notebook.

To see the modeling of the database part of the project please refer to [this specific repository](https://github.com/gabiskli/adventure-works-sales-dw).

# Sales Prediction

The demand prediction problem was broken into 4 main business questions:

- Forecating demand of all products sold to all stores.
- Comparing forecasts done on the previsou item with regression models.
- Comparing demand for different country groups (U.S versus all other countries).
- Forecasting demand of Gloves to calculate how many zippers a global gloves suppliers would need to buy.

All predictions was done with a 3 month horizon. Time series models were used to answer most of the topics above, and a linear regression was done to compare to time series. 

The notebook in this repository has all steps done and analysis troughtout it, including some EDA and Data Preparation process, modeling and than answers to our questions at the end.

## Some considerations and Improvements

Since the goal of this predicitons was to compare to the method done by ADW team now, it was decided to keep it more simple. But there are a few improvements that we can make to make predictions better and to consider other possibilities.

- First off all we could use other time series models to benchmark and study other performances. This could have also be done with regression models. 
- There is also cross validation techinque that could be used to evaluate model's performance over time. It is a relatively simple implementation that can imporve our performance.
- We can also use more hierarchical levels, such as product category, color and size.
- If more hierarchies are added, other reconciliation methods can be done in other to find the best fit.

Besides improvements that can be done, there are a couple considerations on the current implementation:

- From the data provided in the DW only sales performed to Stores (`customer_type = 'Store`) were considered, in order to facilitate analysis. But other category of customers could be added.
- And products that were discontinued were not included in the dataset as well. Since we are studying demand prevision it wouldn't make sens to predict discontinued products.


# Dashboard and Visualizations

The dashbboard was done using the star schema modelled in the first part of this project. The main tool used was PowerBI, which was connected directly with BigQuery to get the data needed.

Since dashboard's target public was operational team of ADW, the idea was to create multiple pages with different visual that could be filtered and cross referenced so they could extract the necessary insights from it. 

The pages structure were divided in the following way:

- Summary: with general information on ADW sales health.
- Products: information about most performatic product category and line.
- Customers: used a RFM analysis done inside the modeling part to study client segmentation.
- Territory: information about market share and performance of countries, states and cities.

Besides the dashboard, a .pdf report was made to be delivered to the CEO. Since this didn't have filtering possibilities all information was done to show current sales status. It contains more KPIs and charts that could help the CEO have a bigger picture of the companies sales health, to make more upper level decisions.

To pages of the dashboard I added a folder with some pictures of pages.
