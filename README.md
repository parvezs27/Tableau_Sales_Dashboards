# Task Context

We are working as Data Analysts for the retail company "Superstore", which sells furniture, office supplies and technology items. We have been tasked with developing two dashboards using Tableau, to assist stakeholders including sales managers and executives, in analysing sales performance and customers. Stakeholders would like a high level view of key metrics and to be able to analyse year-over-year performance. Additionally, stakeholders would like to see an overview of customer data, trends and behaviours, in order to assist management and marketing teams to understand customer segments and improve customer satisfaction.

To tackle this task, we will follow the plan below:

## Analyse Requirements
- Collect and understand task requirements
- Select optimal charts
- Develop Mockups and Prototypes

## Build the Data Source
- Connect data (clean the data if required)
- Create a Data Model
- Check data types and understand the data

## Build the Charts
- Create and test required calculated fields
- Build charts (ensure data is correct through testing/cross referencing with Excel)
- Format charts
  - Remove gridlines and other unnecessary lines
  - Clean up axes and headers
  - Select colors and format tooltips
 
 ## Build the Dashboards
 - Build container structure
 - Input charts
 - Format
   - Layout charts and elements in alignment by utilising functions such as "distribute contents evenly" and inner and outer padding. 
   - Utilise space by fitting to "entire view"
   - Add relevent legends/colour keys
   - Add filters for interactivty
   - Add icons for navigation buttons
- Test the dashboard

# Analysis of Requirements (Sales Dashboard)

## Content Requirements

The requirements below for the Sales Dashboard have been provided to us by management.

KPI Overview:
- Display a high level view of total sales, total profit and quantity sold for current and previous years. 

Sales Trends:
- Visualise data for each KPI on a monthly basis for current and previous years.
- Highlight the months with the highest and lowest sales, whilst making them easily recognisable.

Comparison of product subcategories:
- Compare the sales and profit for the different product subcategories for the current and previous year, including a comparison of sales with profit.

Weekly Trends for Sales & Profits:
- Show the weekly sales and profit for the current year and display the average weekly sales and profit values.
- Highlight the weeks that are above and below the average values.

## Design Requirements

The Sales Dashboard should meet the following design requirements:

- Allow the end user flexibiity to view historical data.
- Allow the end user easy navigatation between dashboards.
- Charts should be interactive, allowing end users to filter data using the charts themselves.
- The dashboard should allow end users to filter by category, subcategory and location (region, state and city).

## Plan to Meet Requirements

Below is our plan to meet the content and design requirements.

**KPI Overview:**

** - Display a high level overview of total sales, profits and quantity for the current and previous year.**

To display the KPI's, we will utilise "BANs" (Big-Ass Numbers). BAN's display key metrics or KPI's in a large, bold format. This offers several benefits, such as:
- Quicker, clearer and easier noticeability of key information. The larger and bolder text has more of a direct impact, allowing critical information to be seen quickly and clearly. This reduces cognitive load on the viewer and having to search around the screen for the key information, ultimately allowing for a better viewing experience.
- Improvement of dashboard structure and reading flow. Having large and bold text at the top of the dashboard to highlight critical information creates a top to bottom visual hierarchy, where the most information is highlighted at the top. This provides dashboard structure and a logical reading flow for the end user.

**Sales Trends:**

** - Visualise data for each KPI on a monthly basis for the current and previous year.**
** - Highlight the months with the highest and lowest sales and make them easily recognisable.**

Since we are required to visualise A) Sales Trends and B) the data for each KPI on a monthly basis for current and previous years, we will use sparklines to achieve this. Sparklines are smaller and simpler line chart without axes and coordinates used to show trends overtime in an uncluttered way. For our task, they will complement the BAN's well, as the BAN's will provide a snapshot of key metrics at a particular point in time, whilst the sparklines will provide the trends overtime for current and previous years (2 lines), providing more context. We will also be able to highlight the highest and lowest selling months on the sparklines. 

**Comparison of product subcategories:**
** - Compare the sales and profit of the different product subcategories for the current and previous year, including a comparison of sales with profit.**

For the comparison of product subcategories, if we were to be comparing subcategories only for the current year, then a regular vertical or horizontal bar chart would be an good choice. However, since we have multiple dimensions (subcategory, current year, previous year) and one measure (sales performance), a bar-in-bar chart would be an ideal chart to display the product subcategory sales and profits by current and previous year. 

Talking about bar charts, they are one of the most commonly used and effective visualisations to communicate information quickly and clearly. There are several features of bar charts that allow for this including the length of the bars which provide an easier comparison of values across different categories, the visual separation between bars which allows for clear distinction between categories and the ability to customise the chart with colours, labels and annotations to emphasise key information.

**Weekly Trends for Sales & Profits:**
**- Show the weekly sales and profit for the current year and display the average weekly sales and profit values.**
** - Highlight the weeks that are above and below the average values.**

For weekly trends for sales and profits, since we are looking at sales and profit data over time on a weekly basis, a line chart would be a good choice chere. The path of the chart can be customised from a linear path to a step path for example. Line charts with a linear path use straight lines between data points, implying a constant rate of change from one data point to the next, which may not always be true. Step line charts can be an effective way to display a more accurate depiciton of the change between data points by showing how long the value at a specific data point lasts or how large a change is between data points. 

**Design Requirements**

- Allow the end user flexibiity to view historical data.
- Allow the end user easy navigatation between dashboards.
- Charts should be interactive, allowing end users to filter data using the charts themselves.
- The dashboard should allow end users to filter by category, subcategory and location (region, state and city).

Paramaters will be utilised to allow end users to view historical data for previous years. Filters will be utilised to allow end users to filter using charts and to filter by category, subcategory and location. Finally, navigation buttons will be included allowing navigation between dashboards.

Now that we have a plan for addressing the requirements, we'll go ahead and create a mockup dashboard.

## Mockup

We have used Figma to create a mockup of our Sales dashboard, link below:
https://www.figma.com/design/DFoayFIDtm6SNWIpFZskPh/Sales-Dashboard?node-id=0-1&t=nWqf2NGtbFsqxyDH-1

Figma is a great tool to use to prototype your dashboards due to it's features and ease of use. In our mockup, we have opted for a clear, uncluttered and minimalist design, by using simple charts, utilising white space and conservative use of colouring (4-5 key colours). The Customers Dashboard will follow a very similar structure to the Sales dashboard.

# Data Source Preparation

We will start by building our data model. It's important to understand the data we have and to see which tables are dimensions and which table are facts. The Customers, Location and Products tables are dimension tables, as the information in these tables contain categorical data that provide context to measures. The Orders table is a fact table, as it contains transactions which are measurable business events. 

Now that we understand our data we can start modeling this data for our use. We will create a relation between each dimension table and the fact table as below. You can think of this model as one fact table, and all the dimension tables are connected to this one fact table to describe the facts. 

![image](https://github.com/user-attachments/assets/01543540-1e77-4a9b-933c-ab27c0bb1a9e)
*Image 1. Data Model* 

Now we will go ahead and check the data types to ensure that Tableau has interpreted and processed the data correctly. It's not uncommon for Tableau to misinterpet the data, hence why it's important to do a manual check. Potential misinterpretations by Tableau may include interpreting Dates as Strings, which won't allow us to analyse the data in relation to time. Additioanlly, numbers can be interpreted as strings, if this happens, we won't be allowed to perform mathematical operations like sum, average or percentage calculations. Upon checking our data, we can see all the data types are correct in our data. Text columns like Product Name have the string data type, numerical columns like Profit have the number data type, date columns have the date data type and location columns have the geographic data type.  

Now that we've analysed our requirements, created a mockup and built our data source, we can move onto the exciting part and start developing our visualisations. 

# Building Charts

## BANs
We will now go ahead and create our BANs, as below:

![image](https://github.com/user-attachments/assets/68d27ea2-67ff-45b1-88e6-6c7e84ec5677)

*Image 2: BANs - KPI values cross-referenced with Excel*

Key points regarding the creation of BANs:
- Calculated fields were created for current year, previous year and the difference between current and previous year. 
- A parameter was created and linked to the calculated fields for current and previous year metrics, to allow dynamic year selection.
- Calculated fields were also created for the % difference between the current and previous years metrics.
- The custom format "▲ 0.0%; ▼ -0.0%" was implemented for the % difference between current and previous year metrics, where the up arrow denotes a positive percent difference and the down arrow denotes a negative percent difference.
- The values of the metrics were cross referenced for all years against Excel. Sometimes Tableau can misinterpret values and misconstrue aggregations. Which is why it's a good idea to double check the values outside of Tableau. In Image 2, we can see that the aggregation for the metrics for the year 2021 are correct. 

## Sparklines

Key points regarding the creation of the Sparklines:

- The calculated field "Min/Max" was created for sales, profit and quantity, in order to return the value for the rows where the metric value is either maximum or minimum in the given window. This will allow us to highlight the maximum and minimum values on the chart. 

After formatting, below are our final KPI charts:

![image](https://github.com/user-attachments/assets/96c598a4-2d34-4254-b07c-514071f72022)
*Image 3. KPI Charts*

The BAN's clearly depict the KPI value, the percent difference is shown between the current and previous year as well sa the sparklines to depict the difference in trends between the years. Axes, tick marks, titles, gridlines and the names of other months have been omitted to reduce cluttering and distraction. 

## Bar in Bar Charts

Key points regarding the creation of the Bar in Bar Charts:

- A calculated field was created "KPI CY Less PY", which shows dots on the subcategories where current year sales were below previous year sales.

After formatting, below are our bar in bar, and bar charts:

![image](https://github.com/user-attachments/assets/5a976db4-2e12-45eb-9835-90729b0b92d3)
*Image 4. Bar in Bar, and Bar Charts*

## Step Line Charts

Key points regarding the creation of the Step Line Charts:

- Weekly sales and weekly profit charts are displayed for the curent year, as well as the average weekly value with a reference line. Dual Axis has not been used, as overlaying one line graph over the other will cause the reference lines to be in too close proximity with each other making it hard to read.
- Orange denotes weeks/time periods below the average weekly value for that year, whereas blue denotes weeks/time periods above the average weekly value for that year.

After formatting, below are our step line charts:

![image](https://github.com/user-attachments/assets/2a5624ce-0650-4c02-a37b-c868b3fc3826)
*Image 5. Step Line Charts*

Now that we have finished our charts, we can now move onto arranging all these charts into the Sales dashboard.

# Building Dashboard

## Sizing:
Sizing dashboards in Tableau can be challenging due to several factors, including the commonly problematic default Tableau scaling, the varied display sizes of end users, and their default zoom levels in computer display settings. It is generally advisable to avoid using Tableau's automatic sizing function. Although automatic sizing may seem convenient, it often leads to issues such as misalignment of elements and improper scaling of floating versus non-floating elements. Additionally, automatically sized dashboards can result in slower performance on Tableau Server. This happens because the server tries to render the dashboard to fit the smallest common screen size among all users, leading to longer load times and potential site crashes.

To mitigate these problems, it is recommended to use fixed-sized dashboards. Fixed-sized dashboards ensure that all elements remain properly aligned and maintain their intended positions. Moreover, when viewed on Tableau Server, fixed-sized dashboards tend to load faster as the server can utilize cached versions, improving overall performance and user experience.

With the decision to use fixed sizing for dashboards, the next question is determining the optimal size. This largely depends on the display sizes that end users will use to view the dashboards. In many organisations, there is a standardised size for all dashboards, simplifying the design process as all end users have similar screen sizes. However, in many cases, end users will view dashboards on various devices, ranging from laptop screens to desktop monitors and larger TV displays. Therefore, it is important to design dashboards in multiple sizes to accommodate these variations.

The PowerPoint sizing option is particularly popular, as many organisations prefer to view and share dashboards as slides. For this project, we will use a custom fixed size of 1200 x 800. In practice, we would assess the screen sizes of end users and develop dashboards tailored to those dimensions. This doesn't mean creating an excessive number of dashboards; a 1200 x 800 dashboard, for instance, will be sufficient for screens of similar sizes. However, where thare are significant differences, such as viewing on smaller laptop screens or phones, will necessitate creating dashboards specifically designed for those smaller formats.

## Containers:

Layout containers could be said to be the ultimate love-hate relationship within Tableau. Whilst containers are great for several things like providing strucutre to your dashboard, assisting with alignment of elements, dynamic resizing and re-usable layouts, they can also be a pain to work with at times. However, if you use them correctly, they will serve you well. 

For our task, we will utilise containers in a manner that minimises mess and the potential for the dashboard to break. The very first primary vertical container, which will hold all subsequent containers, will be floated, coordinates set to 0,0 and size set to the size of the dashboard which is 1200 x 800. By floating the first container which holds all subsequent containers, we will keep nested tiled containers from automatically appearing in the item hierarchy. Tiled containers add extra layers into the item hierarchy which makes it hard to track your containers and your item hierarchy confusing to read. This is not ideal for yourself, nor for others that may need to view the item hierarchy in the future. Keep the item hierarchy clean, we will also label all our containers so we know which container holds which elements and is for which purpose. Also, blank objects will be used as placeholders in our containers to help with inputting our elements into the correct container/correct position in the container. These blank objects become increasingly important when you've got multiple containers around each other and it becomes trickier to drag and drop elements in the correct position. 

Our item hierarchy is looking like this so far. If we had used tiled containers there would be several "tiled" layers in the item hierarchy, causing confusion. 

![image](https://github.com/user-attachments/assets/1f57a467-8359-4251-b97b-120ef7abbe90)
*Image 6. Item Hierarchy 1*


![image](https://github.com/user-attachments/assets/698f2a3a-44c7-4c0b-b595-bf81ad913a60)
*Image 7. Item Hierarchy 2*

Here is the final container structure below. Our primary floating vertical container has the orange border, whilst the 3 horizontal containers within this container are shaded blue. 

![image](https://github.com/user-attachments/assets/132ea26b-8cd0-4097-9a07-e2d421d1ecaf)
*Image 8. Container Structure*

## Final Sales Dashboard

After formatting and re-arranging the elements, below if the final version of the Sales Dashboard.

![image](https://github.com/user-attachments/assets/11bad169-b104-41b2-ab20-9aa64c7eb4d3)


# Analysis of Requirements (Customers Dashboard)

## Content Requirements

The requirements below for the Customers Dashboard have also been provided to us by management:

KPI Overview:

- Display a high level view of the total number of customers, total sales per customer and the total number of orders for the current and previous years.

Customer Trends
- Present data for each KPI on a monthly basis for the current and previous year.
- Identify the months with the highest and lowest sales, highlighting these months for easier recognition. 

Customer Distribution by Number of Orders:
- Provide a representation of the distribution of customers based on the number of orders placed to provide insights into customer behaviour, loyality and engagement. 

Top 10 Customers by Profit:
- Display the top 10 customers by profits in descending order.
- Show additional information such as rank, number of orders, current sales, current profit and the last order date.

## Design Requirements

- Allow the end user flexibiity to view historical data.
- Allow the end user easy navigatation between dashboards.
- Charts should be interactive, allowing end users to filter data using the charts themselves.
- The dashboard should allow end users to filter by category, subcategory and location (region, state and city).

## Plan to Meet Requirements

Below is our plan to meet the content and design requirements.

**KPI Overview:**

- **Display a high level view of the total number of customers, total sales per customer and the total number of orders for the current and previous years.**

**Customer Trends**
- **Present data for each KPI on a monthly basis for the current and previous year.**
- **Identify the months with the highest and lowest sales, highlighting these months for easier recognition.**

The KPI Overview and Customer Trend requirements are very similar to the KPI requirements and Sales Trends for the Sales Dashboard above. Hence, the plan to meet these requirements will be exactly the same. BAN's will be used to display the KPI's whilst sparklines will be used to showcase customer trends overtime. 

**Customer Distribution by Number of Orders:**

- **Provide a representation of the distribution of customers based on the number of orders placed to provide insights into customer behaviour, loyality and engagement.**

For customer distribution by number of orders, a histogram will be used. A histogram will help in understanding how many customers fall into the different ranges (bins) of the number of orders placed, providing picture of the overall distribution. Additionally, the histogram will also allow the spotting of outliers or unusual data points that may indicate unique customer segements or behaviours. 

**Top 10 Customers by Profit:**
- **Display the top 10 customers by profits in descending order.**
- **Show additional information such as rank, number of orders, current sales, current profit and the last order date.**

For Top 10 Customers by Profit, a simple table will be used. Due to the amount of detail we have to display, a table with the metrics as columns and ranks as rows will provide a picture of the information required. 

Paramaters will be utilised to allow end users to view historical data for previous years. Filters will be utilised to allow end users to filter using charts and to filter by category, subcategory and location. Finally, navigation buttons will be included allowing navigation between dashboards.

We won't create a mockup for the Customer Dashboard, as it will be the exact same structure as the Sales Dashboard. We will also skip Data Source Preparation as we already have the data source prepared.

# Building Charts

## BANs

We will follow the exact same process here as we did for the Sales Dashboard, which is to create the required calculated fields, test these fields and test the aggregated values against Excel. 

## Sparklines

The same process as the Sales Dashboard will be followed here too.

## Histogram and Weekly Trends for Sales and Top 10 Customers by Profit

To show the customer distribution, since we are talking aboout two measures 1) Count of customers and 2) Count of orders, we have to use an LOD (level of detail) expression to generate the bins for the histogram and find the total number of orders for each customer for the current year. The LOD expression used is below.

```
{ FIXED [CY Customers]: COUNTD([CY Orders])}

```

For the Top Customers by Profit table, we used the INDEX() function to assign a rank to the rows. The default table were also removed and replaced with custom headers using text objects within a horizontal container. 


# Building Dashboard

## Final Sales Dashboard

The sizing and container structure will be exactly the same as the Sales Dashboard. The only primary differences between the two dashboard are the different charts, and the navigation buttons which turn white when active on that particular dashboard. 

After formatting and re-arranging the elements, below if the final version of the Customers Dashboard.

![image](https://github.com/user-attachments/assets/3a4c4d59-995c-4712-9922-f1a977306100)







