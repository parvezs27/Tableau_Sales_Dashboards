# Task Context

We are working as Data Analysts for the retail company "Superstore", which sells furniture, office supplies and technology items. We have been tasked with developing two dashboards utilising Tableau to assist stakeholders, including sales managers and executives to analyse sales performance and customers. Stakeholders would like a high level view of key metrics and to be able to analyse year-over-year sales performance. Stakeholders have mentioned the below as primary requirements for the dashboards.

## Content Requirements

KPI Overview:
Display a high level overview of total sales, profits and quantity for the current and previous year.

Sales Trends:
- Visualise data for each KPI on a monthly basis for the current and previous year.
- Highlight the months with the highest and lowest sales and make them easily recognisable.

Comparison of product subcategories:
- Compare the sales and profit for the different product subcategories for the current and previous year.

Weekly Trends for Sales & Profits:
- Show weekly sales and profit for curent year and display the average weekly values.
- Highlight the weeks that are above and below the average to draw attentio nto sales & profit performance.

## Design Requirements

- The dashboard should allow the end user flexibiity to see historical data.
- The dashboard should allow the end user to navigate between dashboards easily.
- The charts should be interactive, allowing end users to filter data using the charts themselves.
- The dashboard should allow end users to filter by category, subcategory and by location such as by region, state and city.

## Plan to Meet Requirements

To display the KPI's we will utilise "BANs" (Big-Ass Numbers), which are simple and effective to clearly display key metrics on Tableau dashboards. 

For sales trends, since the KPI data will be overtime (over the current year and over the previous year on a monthly basis), we can utilise sparklines to showcase this. Sparklines are small and simple line charts which are effective for quickly communicating trends over time within a compact space. For our dashboard, whilst KPI BANs will provide a snapshot of performance at a particular point in time, sparklines will provide a quick view of the trends overtime, as well as allow to us display the highest and lowest selling months. 

For product subcategory comparison, if we were to be comparing subcategories only for the current year, then a regular vertical or horizontal bar chart sorted in descending order would be ideal. However since we have multiple dimensions (subcategory, current year, previous year) and one measure (sales performance), a bar-in-bar chart would be effective to display the product subcategory sales and profits by current and previous year. 

Talking about bar charts, they are one of the most effective and flexible visualisations to use to communicate information quickly and clearly. There are several features of bar charts that allow for this including the length of the bars which allow for an easier comparison of values across different categories, the visual separation between bars which allows for clear distinction between categories and the ability to customise the chart with colours, labels and annotations to emphasise key information. 

For weekly trends for sales and profits, since are looking at sales and profit data over time (current year) on a weekly basis, a line chart would be the ideal chart to use. 

For dashboard interactivity, paramaters will be utilised to allow end users to see historical data, buttons will be used to allow end users to navigate between dashboards easily and filters will be used to allow filtering using charts and by location.

Now that we have a plan for how we'll address the content and design, we will now create a mockup dashboard. 

## Mockup

I have gone ahead and used Figma to create a mockup of our dashboard which meets our requirements here: https://www.figma.com/design/DFoayFIDtm6SNWIpFZskPh/Sales-Dashboard?node-id=0-1&t=nWqf2NGtbFsqxyDH-1

Figma is a fantastic tool to use to prototype your dashboards due to it's features and ease of use allowing you to whip up mockups efficiently. 

## Data Source Preparation

We will start by building our data model. It's important to understand the data here and see which tables are dimensions and which table are facts. The Customers, Location and Products tables are dimension tables, as the information in these tables contain categorical data that provide context to measures. The Orders table is a fact table as it contains transactions which are measurable business events. 

Now that we understand our data we can start modeling. We will create a relation between each dimension table and the fact table, as below. You can think of as one fact table and all the dimension tables are connected to this fact table to describe the facts. 

![image](https://github.com/user-attachments/assets/01543540-1e77-4a9b-933c-ab27c0bb1a9e)

Now we'll go ahead and check our data types to ensure that Tableau has interpreted and processed the data correctly. It's not uncommon for Tableau to misinterpet the data, hence why it's important to do a manual check yourself. Potential misinterpretations by Tableau may include interpreting Dates as Strings, which in doing so won't allow looking at the data in relation to time, or numbers as strings, which won't allow us to perform mathematical operations like sum, average or percentage calculations. Upon checking we can see all the data types are correct in our data. Text columns like Product Name have the string data type, numerical columns like Profit have the number data type, date columns have the date data type and location columns have the geographic data type.  

By now it's a good idea to explore the data and become familiar with the structure of it, so you don't have to do a whole lot of figuring out during your visualisation building. 

Now that we've analysed our requirements, created a mockup and built our data source, we can move onto the fun part and start developing our visualisations. 

# Building Charts

## BANs
We will now go ahead and create our BANs. Here are the specific requirements we'll be addressing using BANs:
- Display a high level overview of total sales, profits and quantity for the current and previous year.
- The dashboard should allow the end user flexibiity to see historical data.

Below are our BANs:

Key points regarding the creation of the BANs:
- A calculated field was created for current year metrics and previous year metric, as we want to display the comparison between metrics (sales, profit and quantity).
- A parameter was created and linked to the calculated fields for current and previous year metrics, to allow end users to dynamically select the year.
- A calculated field was also created for the % difference between the current and previous years.
- The number format "▲ 0.00%; ▼ -0.00%" was implemented, whereby the up arrow is displayed if the perent difference is a positive number and the down arrow is displayed if the percent difference is a negative number.

## Sparklines
Here are the reqirements we'll be addressing using sparklines:
- Visualise data for each KPI on a monthly basis for the current and previous year.

Key points regarding the creation of the Sparklines:
- The calculated field "Min/Max" Sales was created to return the sales value for the rows where the sales are either maximum or minimum in the given window. This will allow us to highlight the maximum and minimum values on the chart. 

Key points regarding chart:


CONTAINERS
Tiled can get messy as below, compare to containers it is much cleaner and easier to read. Floating the first vertical container keeps nested tiled container from automatically appearing. It makes the dashboard easier to organise and it will scale when changing the ssize of the dashboard. Naming the containers also help with organisation and helping other users with understanding the contents of the dashboard. Blanks will be added to containers as placeholders and colored to see where they are.
