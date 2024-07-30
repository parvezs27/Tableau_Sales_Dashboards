# Task Context

We are working as Data Analysts for the retail company "Superstore", which sells furniture, office supplies and technology items. We have been tasked with developing two dashboards utilising Tableau to assist stakeholders, including sales managers and executives, to analyse sales performance and customers. Stakeholders would like a high level view of key metrics and to be able to analyse year-over-year sales performance. Additionally, stakeholders would like an overview of customer data, trends and behaviours, in order to assist management and marketing teams to understand customer segments and improve customer satisfaction.

To tackle this task, we will follow the plan below:

## Analyse Requirements
- Collect and understand requirements
- Select Charts
- Develop Mockups and Prototypes

## Build the Data Source
- Connect Data
- Create a Data Model
- Check Data Types and Understand the Data

## Build the Charts
- Create and test Calculated Fields
- Build Chart
- Format
  - Remove gridlines and other unnecessary lines
  - Clean up axes and headers
  - Choose colors and format tooltips
 
 ## Build the Dashboards
 - Build container structure
 - Input Charts
 - Format
   - Layout charts and elements in alignment by utilising functions such as "distribute contents evenly" and inner and outer padding. 
   - Utilise space by fitting to "entire view"
   - Add relevent Legends
   - Add filters for interactivty
   - Add icons for navigation buttons

# Sales Dashboard

## Content Requirements

The below requirements for the Sales Dashboard have been provided to us by management.

KPI Overview:
- Display a high level overview of total sales, profits and quantity for the current and previous year.

Sales Trends:
- Visualise data for each KPI on a monthly basis for the current and previous year.
- Highlight the months with the highest and lowest sales and make them easily recognisable.

Comparison of product subcategories:
- Compare the sales and profit for the different product subcategories for the current and previous year, including a comparison of sales with profit.

Weekly Trends for Sales & Profits:
- Show weekly sales and profit for curent year and display the average weekly values.
- Highlight the weeks that are above and below the average to draw attentio nto sales & profit performance.

## Design Requirements

The Sales Dashboard should meet the following design requirements:

- Allow the end user flexibiity to see historical data.
- Allow the end user to navigate between dashboards easily.
- The charts should be interactive, allowing end users to filter data using the charts themselves.
- The dashboard should allow end users to filter by category, subcategory and by location such as by region, state and city.

## Plan to Meet Requirements

Below is our plan to meet the content and design requirements:

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

To double check if our totals are fine, we cross check with Excel and get the sums of sales, profit and quantity. Below we can see that the sales, profit and quantity totals for 2021 match what's shown in Tableau. 

![image](https://github.com/user-attachments/assets/68d27ea2-67ff-45b1-88e6-6c7e84ec5677)

The same was repeated for the percent increase between years. 

## Subcategory Comparison

Specific requirements to be addressed:
- Compare the sales and profit for the different product subcategories for the current and previous year, including a comparison of sales with profit.

A calculated field has been created to show dots on the subcategories where current year sales were below previous year sales. 

## Weekly Trends for Sales and Profit

Specific requirements to be addressed:
- Show weekly sales and profit for curent year and display the average weekly values.
- Highlight the weeks that are above and below the average to draw attention to sales & profit performance.


In the line charts the weekyl sales and profit are displayed for the curent year, as well as the average weekly value with a reference line. We have not utilised a Dual Axis here as overlaying one line graph over the other will cause the reference the lines to be too close to each other making it hard to read, keeping the line graphs separate keeps the chart neat and easier to read. 

The path in this chart could be kept as linear, which is absolutely fine, but we decided to change it up a little but making the chart a bit more interesting with a step path. 

Now that we've finished our charts, we can now move onto arranging all these charts onto a dashboard.

# Building Dashboard

### Sizing:
Sizing dashboards can be tricky due to various factors such as the problematic default Tableau scaling, the various displays sizes of the various end users, as well as the default zoom levels in the computer display settings of the end users. Generally, it's best to start with avoiding Tableau's automatic sizing. Whilst it sounds like the ideal option to go with, what tends to happen is that your dashboard can break when scaling. Alignments become misaligned, floating elements may not scale up/down with the rest of the non-floating elements and viewing an automatically sized dashboard on Tableau Server can be slower. This tends to be the case when multiple users are accessing the dashboard on Tableau Server, the server renders the screen size to find the lowest common denominator screen size among all the people viewing the dashboard, causing slower load times and site crashes. To avoid all these issues, fixed sized dashboards are recommended. Dashboard elements stay in place and when viewed on Tableau Server, they tend to load faster as a cached version will be used on the server. 

Now that we know we should be using fixed sizing, the question arises, what size is best? This is determined by what size displays the end users will be using to view the dashboards on. In many companies, there is a fixed standard sizing to be used for all dashboards, as the size of the screens of the end users will be the same. This makes life much easier. However, a lot of the time this won't be the case, as end users will likely be viewing the dashboards on various screens from laptop screens, to desktop monitors to larger TV displays. Which is why it's important to have your dashboard in various sizes to accommodate for the variances in screen sizes. The PowerPoint sizing option is popular, as management in many companies prefer to view and share dashboards as slides. 

For this project, we will utilise a custom fixed size of 1200 x 800, however, in the real world we will obtain a better understanding of the screen sizes of the end users and develop several dashboards accommodating to those sizes. This doesn't mean we have to develop 20 different dashboards for each different size, as a 1200 x 800 dashboard for example will be fine for screen sizes around the same size (above or below). However where there's a bigger difference, for example if the dashboard needs to be viewed on a smaller laptop screen or phone, that's when we'll create a dashboard accommodating for the sizes at that level of smaller viewing. 

### Filtering




CONTAINERS
Tiled can get messy as below, compare to containers it is much cleaner and easier to read. Floating the first vertical container keeps nested tiled container from automatically appearing. It makes the dashboard easier to organise and it will scale when changing the ssize of the dashboard. Naming the containers also help with organisation and helping other users with understanding the contents of the dashboard. Blanks will be added to containers as placeholders and colored to see where they are. 

Your item hierarchy should be looking like this. With tiled containers there would be extra layers which make it all confusing. 

![image](https://github.com/user-attachments/assets/1f57a467-8359-4251-b97b-120ef7abbe90)
![image](https://github.com/user-attachments/assets/698f2a3a-44c7-4c0b-b595-bf81ad913a60)

All the contents in the containers have been distributed evenly. Some can be trickier like the navigation buttons at the top, so we had inserted them both inside a horizontal container and then distributed them evenly. 







# Customer Dashboard

## Content Requirements

KPI Overview:
Display a summary of the total number of customers, total sales per customer and the total number of orders for the current and previous year. 

Customer Trends
- Present data for each KPI on a monthly basis for the current and previous year.
- Identify the months with the highest and lowest sales, highlighting these mnths for easier recognition. 

Customer Distribution by Number of Orders:
- Provide a representation of the distribution of customers based on the number of orders placed in order to provide insights into customer behaviour, loyality and engagement. 

Top 10 Customers by Profit:
- Display the top 10 customers by profits generated in descending order.
- Show additional information such as rank, number of orders, current sales, current profit and the last order date.

## Design Requirements

- The dashboard should allow the end user flexibiity to see historical data.
- The dashboard should allow the end user to navigate between dashboards easily.
- The charts should be interactive, allowing end users to filter data using the charts themselves.
- The dashboard should allow end users to filter by category, subcategory and by location such as by region, state and city.

## Plan to Meet Requirements

The KPI Overview and Customer Trend requirements are very similar to the requirements for the Sales Dashboard above. Hence, the plan to meet these requirements will be exactly the same. BAN's will be used to display the KPI's whilst sparklines will be used to showcase customer trends overtime. 

For customer distribution by number of orders, a histogram will be used. Histograms will help in understanding how many customers fall into the different ranges (bins) of the number of orders placed, providing a clear picture of the overall distribution. Additionally, the histogram will also allow the spotting of outliers or unusual data points that may indicate unique customer segements or behaviours. 

For product subcategory comparison, if we were to be comparing subcategories only for the current year, then a regular vertical or horizontal bar chart sorted in descending order would be ideal. However since we have multiple dimensions (subcategory, current year, previous year) and one measure (sales performance), a bar-in-bar chart would be effective to display the product subcategory sales and profits by current and previous year. 

For top 10 customers by highest profit, a table will be used. Due to the amount of detail we have to display, a simple table with the metrics as columns and ranks as rows will provide a clear picture. 

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

To double check if our totals are fine, we cross check with Excel and get the sums of sales, profit and quantity. Below we can see that the sales, profit and quantity totals for 2021 match what's shown in Tableau. 

![image](https://github.com/user-attachments/assets/68d27ea2-67ff-45b1-88e6-6c7e84ec5677)

The same was repeated for the percent increase between years. 

## Subcategory Comparison

Specific requirements to be addressed:
- Compare the sales and profit for the different product subcategories for the current and previous year, including a comparison of sales with profit.

A calculated field has been created to show dots on the subcategories where current year sales were below previous year sales. 

## Weekly Trends for Sales and Profit

Specific requirements to be addressed:
- Show weekly sales and profit for curent year and display the average weekly values.
- Highlight the weeks that are above and below the average to draw attention to sales & profit performance.


In the line charts the weekyl sales and profit are displayed for the curent year, as well as the average weekly value with a reference line. We have not utilised a Dual Axis here as overlaying one line graph over the other will cause the reference the lines to be too close to each other making it hard to read, keeping the line graphs separate keeps the chart neat and easier to read. 

The path in this chart could be kept as linear, which is absolutely fine, but we decided to change it up a little but making the chart a bit more interesting with a step path. 

Now that we've finished our charts, we can now move onto arranging all these charts onto a dashboard.

# Building Dashboard

### Sizing:
Sizing dashboards can be tricky due to various factors such as the problematic default Tableau scaling, the various displays sizes of the various end users, as well as the default zoom levels in the computer display settings of the end users. Generally, it's best to start with avoiding Tableau's automatic sizing. Whilst it sounds like the ideal option to go with, what tends to happen is that your dashboard can break when scaling. Alignments become misaligned, floating elements may not scale up/down with the rest of the non-floating elements and viewing an automatically sized dashboard on Tableau Server can be slower. This tends to be the case when multiple users are accessing the dashboard on Tableau Server, the server renders the screen size to find the lowest common denominator screen size among all the people viewing the dashboard, causing slower load times and site crashes. To avoid all these issues, fixed sized dashboards are recommended. Dashboard elements stay in place and when viewed on Tableau Server, they tend to load faster as a cached version will be used on the server. 

Now that we know we should be using fixed sizing, the question arises, what size is best? This is determined by what size displays the end users will be using to view the dashboards on. In many companies, there is a fixed standard sizing to be used for all dashboards, as the size of the screens of the end users will be the same. This makes life much easier. However, a lot of the time this won't be the case, as end users will likely be viewing the dashboards on various screens from laptop screens, to desktop monitors to larger TV displays. Which is why it's important to have your dashboard in various sizes to accommodate for the variances in screen sizes. The PowerPoint sizing option is popular, as management in many companies prefer to view and share dashboards as slides. 

For this project, we will utilise a custom fixed size of 1200 x 800, however, in the real world we will obtain a better understanding of the screen sizes of the end users and develop several dashboards accommodating to those sizes. This doesn't mean we have to develop 20 different dashboards for each different size, as a 1200 x 800 dashboard for example will be fine for screen sizes around the same size (above or below). However where there's a bigger difference, for example if the dashboard needs to be viewed on a smaller laptop screen or phone, that's when we'll create a dashboard accommodating for the sizes at that level of smaller viewing. 

### Filtering



