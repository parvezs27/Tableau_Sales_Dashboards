# Project Links

1. Completed Dashboards on Tableau Public can be accessed [here](https://public.tableau.com/views/SalesandCustomerSuperstoreDashboards/SalesDashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).
2. Data Source can be accessed [here](https://github.com/parvezs27/Tableau_Sales_Dashboards/tree/main/Data%20Source).
3. Figma Mockup/Wireframe can be accessed [here](https://www.figma.com/design/DFoayFIDtm6SNWIpFZskPh/Sales-Dashboard?node-id=0-1&t=nWqf2NGtbFsqxyDH-1).
4. Dashboard Documentation can be accessed [here](https://github.com/parvezs27/Tableau_Sales_Dashboards/blob/main/Dashboards%20and%20Documentation/Sales%20and%20Customer%20Dashboard%20Document.pdf). 

# Task Context

We are working as Data Analysts for the retail company "Superstore", which sells furniture, office supplies and technology products. We have been tasked with developing two dashboards using Tableau, to assist stakeholders including sales managers and executives, in analysing sales performance and customers. Stakeholders would like to a high level view of key metrics and to be able to analyse year-over-year performance. Additionally, stakeholders would like to see an overview of customer data, trends and behaviours, in order to assist management and marketing teams to understand customer segments and improve customer satisfaction.

To tackle this task, we will follow the plan below:

## Analyse Requirements, Select Data Source & Create Documentation
- Collect and understand task requirements.
- Identify and select data source/s.
- Create project documentation (project purpose, dashboard use instructions, version control etc.).
- Select optimal charts.
- Develop mockups and prototypes.

## Build the Data Source
- Data Wrangling (importing, cleaning, transformation).
- Create a Data Model.

## Build the Charts
- Create and test required calculated fields.
- Build charts.
- Test/validate chart totals/aggregations.
- Format charts
  - Remove gridlines and other unnecessary lines/borders.
  - Clean up axes and headers.
  - Select colours and format tooltips.
  - Add necessary highlights to emphasise key data points.
 
 ## Build the Dashboards
 - Build container structure.
 - Input charts.
 - Format
   - Utilise functions e.g. "distribute contents evenly" and inner and outer padding to align elements evenly.
   - Utilise space by fitting charts to "entire view".
   - Add relevent legends/colour keys.
   - Add interactive elements e.g. filters and parameters.
   - Add icons for navigation buttons.
- Test the dashboard and optimise performance.

# Requirements Analysis, Data Source & Documentation (Sales Dashboard)

## Data Source

Management has provided the necessary data to complete the task, accessible [here](https://github.com/parvezs27/Tableau_Sales_Dashboards/tree/main/Data%20Source). 

The data comprises of four CSV files: 'Customers', 'Location', 'Orders' and 'Products', which have already been cleaned. 

## Content Requirements

The content requirements for the Sales Dashboard have been provided to us by management below.

**KPI Overview:**
- Display a high level view of total sales, total profit and total quantity sold for current and previous years. 

**Sales Trends:**
- Visualise data for each KPI on a monthly basis for current and previous years.
- Highlight the months with the highest and lowest sales, whilst making them easily recognisable.

**Comparison of product subcategories:**
- Compare the sales and profit for the different product subcategories for the current and previous years, including a comparison of sales with profit.

**Weekly Trends for Sales & Profits:**
- Show the weekly sales and profit for the current year and display the average weekly sales and profit values.
- Highlight the weeks that are above and below the overall average weekly sales and profit values for the year in view. 

## Design Requirements

The Sales Dashboard should meet the following design requirements:

- Allow the end user flexibiity to view historical data.
- Allow the end user easy navigatation between dashboards.
- Interactive charts, allowing end users to filter data using the charts.
- The dashboard should allow end users to filter by category, subcategory and location (region, state and city).

## Strategy to Meet Content and Design Requirements

Below is our plan to meet the content and design requirements.

**KPI Overview:**

- **Display a high level overview of total sales, profits and quantity for the current and previous year.**

To display the required KPI's, we will utilise **"BANs" (Big-Ass Numbers).** BAN's showcase key metrics or KPI's in a larger, bolder format, which offers several benefits such as:

**Quicker, clearer and easier noticeability of key information:** The larger and bolder text has more of a direct/striking impact, allowing critical information to be seen quickly and clearly. This lessens the cognitive load on the viewer and eliminates the need to search around the screen for key information, ultimately providing a better user experience. 

**Improvement of dashboard structure and reading flow:** Positioning large, bold text at the top of the dashboard to highlight critical information creates a top to bottom visual hierarchy, where the most important information is highlighted at the top. This design creates a well organised dashboard with a logical reading flow for the end user. 

**Sales Trends:**

- **Visualise data for each KPI on a monthly basis for the current and previous year.**
- **Highlight the months with the highest and lowest sales and make them easily recognisable.**

Since we are required to visualise A) Sales Trends, and B) the data for each KPI on a monthly basis for current and previous years, we will use **sparklines** to achieve this. Sparklines are smaller and simpler line chart without axes and coordinates, which are used to show trends overtime in an uncluttered and minimalistic manner. For our task, they will complement the BAN's, as the BAN's will provide a snapshot of key metrics at a particular point in time, whilst the sparklines will illustrate the trends overtime for current and previous years (2 lines), providing more context. Additionally, we will also be able to highlight the highest and lowest selling months on the sparklines. 

**Comparison of product subcategories:**
- **Compare the sales and profit of the different product subcategories for the current and previous year, including a comparison of sales with profit.**

For the comparison of product subcategories, if we were to be comparing subcategories only for the current year, then a vertical or horizontal bar chart would be fine. However, since we have multiple dimensions (subcategory, current year, previous year), and one measure (sales performance), a **bar-in-bar chart** would be an ideal chart to display the product subcategory sales and profits by current and previous year. 

Talking about bar charts, they are one of the most commonly used and effective visualisations to communicate information quickly and clearly. There are several features of bar charts that allow for this including the length of the bars which provide an easier comparison of values across different categories, the visual separation between bars which allows for clear distinction between categories and the ability to customise the chart with colours, labels and annotations to emphasise key information.

**Weekly Trends for Sales & Profits:**
- **Show the weekly sales and profit for the current year and display the average weekly sales and profit values.**
- **Highlight the weeks that are above and below the average values.**

For weekly trends for sales and profits, since we are looking at sales and profit data over time on a weekly basis, a line chart would be a good choice here. The path of the chart can be customised from a linear path to a step path for example. Line charts with a linear path use straight lines between data points, implying a constant rate of change from one data point to the next, which may not always be true. **Step line charts** can be an effective way to display a more accurate depiciton of the change between data points by showing how long the value at a specific data point lasts or how large a change is between data points. 

**Design Requirements**

- Allow the end user flexibiity to view historical data.
- Allow the end user easy navigatation between dashboards.
- Interactive charts, allowing end users to filter data using the charts.
- The dashboard should allow end users to filter by category, subcategory and location (region, state and city).

Parameters will be employed to enable end users to access historical data from previous years. For interactivity, dimension, date, and action filters will be implemented, allowing end users to filter data via the charts, as well as by category, subcategory, and location. Additionally, navigation buttons will be incorporated to facilitate easy navigation between dashboards.

Now that we have a plan for addressing the requirements, we will go ahead and create a mockup dashboard.

## Mockup

We have used Figma to create a mockup/wireframe of our Sales dashboard, accessible [here](https://www.figma.com/design/DFoayFIDtm6SNWIpFZskPh/Sales-Dashboard?node-id=0-1&t=nWqf2NGtbFsqxyDH-1). 

Figma is a great tool to use to prototype your dashboards due to it's features and ease of use. In our mockup, we have opted for a clear, uncluttered and minimalist design, by using simple charts, utilising white space and conservative use of colouring (4-5 key colours). The Customers Dashboard will also follow a very similar structure to the Sales dashboard.

## Documentation

The documentation we have created and will use for this project can be accessed [here](https://github.com/parvezs27/Tableau_Sales_Dashboards/blob/main/Dashboards%20and%20Documentation/Sales%20and%20Customer%20Dashboard%20Document.pdf). 

Dashboard documentation is a best practice and it's crucial that documentation is developed for our dashboards and projects. Documentation provides clarity and guidance to end users, ensuring they understand the purpose and benefits of the dashboard within the context of the business problem/question, the functionality of the dashboard and how to use it optimally. Additionally, documentation holds key information such as data source information and maintenance/update details, which ensure transparency, accountability and preservation of dashboard integrity. 

The documentation for this dashboard will be kept in a separate file. Dashboard documentation should be kept outside of the dashboard rather than embedded inside the dashboard. Embedding documentation within a Tableau dashboard can create several issues. It consumes space, which in turn reduces space for visualisations and other elements. Frequent updates become cumbersome as they require republishing the entire dashboard, and managing version control becomes challenging. User experience can be negatively impacted due to navigation difficulties and limited flexibility in accessing documentation. Additionally, extensive embedded documentation can negatively impact load times and overall dashboard performance. Therefore, keeping documentation separate is ideal for efficiency and a better user experience.

# Data Source Preparation

We will start by building our data model. It is important to understand the data we have and to see which tables are dimensions and which tables are facts. The Customers, Location and Products tables are dimension tables, as the information in these tables contain categorical data that provide context to measures. The Orders table is a fact table, as it contains transactions which are measurable business events. 

Now that we understand our data we can start modeling this data for our use. We will create a relation between each dimension table and the fact table as below. You can think of this model as one fact table, and all the dimension tables are connected to this one fact table to describe the facts. 

![image](https://github.com/user-attachments/assets/01543540-1e77-4a9b-933c-ab27c0bb1a9e)

*Image 1. Data Model* 

Now we will go ahead and check the data types to ensure that Tableau has interpreted and processed the data correctly. It is not uncommon for Tableau to misinterpet the data, hence why it is important to do a manual check. Potential misinterpretations by Tableau may include interpreting Dates as Strings, which won't allow us to analyse the data in relation to time. Additionally, numbers can be interpreted as strings, if this happens, we won't be allowed to perform mathematical operations like sum, average,  percentage calculations etc. Upon checking our data, we can see all the data types are correct. Text columns like Product Name have the string data type, numerical columns like Profit have the number data type, date columns have the date data type and location columns have the geographic data type.  

Now that we have analysed our requirements, created a mockup and documentation template, and built our data source, we can move onto the exciting part and start developing our visualisations. 

# Building Charts

## BANs
We will now go ahead and create our BANs, as below.

![image](https://github.com/user-attachments/assets/68d27ea2-67ff-45b1-88e6-6c7e84ec5677)

*Image 2: BANs - KPI values validated with Excel*

Key points regarding the creation of BANs:
- Calculated fields were created for current year, previous year and the difference between current and previous year. 
- A parameter was created and linked to the calculated fields for current and previous year metrics, to allow dynamic year selection.
- Calculated fields were also created for the % difference between the current and previous years metrics.
- The custom format "▲ 0.0%; ▼ -0.0%" was implemented for the % difference between current and previous year metrics, where the up arrow denotes a positive percent difference and the down arrow denotes a negative percent difference.
- The values of the metrics were validated for all years with Excel. Sometimes Tableau can misinterpret values and misconstrue aggregations, which is why it is a good idea to double check the values outside of Tableau. In Image 2, we can see that the aggregations for the metrics of the year 2021 are correct. 

## Sparklines

Key points regarding the creation of the Sparklines:

- The calculated field "Min/Max" was created for sales, profit and quantity, in order to return the value for the rows where the metric value is either maximum or minimum in the given window. This will allow us to highlight the maximum and minimum values on the chart. 

After formatting, our final KPI charts are below:

![image](https://github.com/user-attachments/assets/96c598a4-2d34-4254-b07c-514071f72022)
*Image 3. KPI Charts*

The BAN's clearly depict the KPI value, the percent difference is shown between the current and previous year, the sparklines showcase the difference in trends between the current and previous year, and, the orange and blue dots represent the months with the lowest and highest value of the particular KPI respectively. Axes, tick marks, titles, gridlines and the names of other months have been omitted to keep a minimalistic and clutter free layout.

## Bar in Bar and Bar Charts

Key points regarding the creation of the Bar in Bar, and Bar Charts:

- A calculated field named "KPI CY Less PY" was created to highlight subcategories where current year sales were below previous year sales. Orange dots have been used to draw attention quickly and easily to these subcategories, indicating lower sales in the current year compared to the previous year.
- The black bars represent the current year, while the grey bars represent the previous year. If a black bar is smaller than a grey bar, it indicates that the product subcategory's sales for the current year were lower than those of the previous year.
- The blue bars represent a profit for the current year in view, whilst the orange bars represent a loss for the current year in view for that particular product subcategory.

After formatting, below are our bar in bar, and bar charts:

![image](https://github.com/user-attachments/assets/5a976db4-2e12-45eb-9835-90729b0b92d3)
*Image 4. Bar in Bar, and Bar Charts*

## Step Line Charts

Key points regarding the creation of the Step Line Charts:

- Weekly sales and weekly profit charts are displayed for the current year in view, along with the average weekly sales and profit values for the year, indicated by a reference line. Dual axis has not been used to avoid overlapping line graphs, which would place the reference lines too close to each other, making them difficult to read
- Orange denotes weeks/time periods below the average weekly value for the year in view, whereas blue denotes weeks/time periods above the average weekly value for the year in view.

After formatting, below are our step line charts:

![image](https://github.com/user-attachments/assets/2a5624ce-0650-4c02-a37b-c868b3fc3826)
*Image 5. Step Line Charts*

Now that we have finished our charts, we can now move onto arranging all these charts into the Sales dashboard.

# Building Dashboard

## Sizing
Sizing dashboards in Tableau presents several challenges due to factors such as the default Tableau scaling, the varied display sizes of end users, and their default zoom levels in computer display settings. Although Tableau's automatic sizing option might initially appear to be the optimal choice, it often results in issues like misalignment of elements and improper scaling of floating versus non-floating elements. Moreover, automatically sized dashboards can lead to slower performance on Tableau Server. This occurs because the server attempts to render the dashboard to accommodate the smallest common screen size among all users, which can increase load times and potentially cause site crashes

To mitigate these problems, it is recommended to use fixed-sized dashboards. Fixed-sized dashboards ensure that all elements remain properly aligned and maintain their intended positions. Additionally, when viewed on Tableau Server, fixed-sized dashboards tend to load faster as the server can utilise cached versions, improving overall performance and user experience.

Now that we have decided to use fixed sizing for the dashboard , the next question is determining the optimal size of the dashboard. This largely depends on the display sizes that end users will use to view the dashboards. In many organisations, there is a standardised size for all dashboards, which simplifies the design process, as all end users have similar screen sizes. However, in many cases, end users will view dashboards on various devices, ranging from laptop screens to desktop monitors and larger TV displays. Therefore, it is important to design dashboards in multiple sizes to accommodate these variations.

The PowerPoint sizing option is particularly popular, as many organisations prefer to view and share dashboards as slides. For this project, we will use a custom fixed size of 1200 x 800. In practice, we would assess the screen sizes of end users and develop dashboards tailored to those dimensions. This doesn't mean creating an excessive number of dashboards; a 1200 x 800 dashboard, for instance, will be sufficient for screens of similar sizes. However, when there are significant differences, such as viewing on smaller laptop screens or phones, this will necessitate creating dashboards specifically designed for those smaller formats.

## Containers

Layout containers may be the ultimate love-hate relationship within Tableau. Whilst containers are great for several uses like providing structure to your dashboard, assisting with alignment of elements, dynamic resizing and creation of re-usable layouts, they can also be a pain to work with. 

For our task, we will utilise containers in a way that minimises mess and reduces the risk of the dashboard breaking. The primary vertical container, which will hold all subsequent containers, will be floated, with its coordinates set to 0,0 and its size configured to match the dashboard dimensions of 1200 x 800. By floating this primary container, we prevent nested tiled containers from automatically appearing in the item hierarchy. Tiled containers add unnecessary layers to the item hierarchy, making it difficult to track and understand, which is not ideal for you or other users who may need to view the item hierarchy.

To maintain a clean item hierarchy, we will label all containers clearly, indicating which elements they hold. Additionally, we will use blank objects as placeholders within our containers to assist with positioning elements correctly. These blank objects are especially important when working with multiple containers around each other, as they assist in the accurate placement of elements.

Below is our item hierarchy, which appears clean and clearly labeled, without any unnecessary layers. If we had used tiled containers, the item hierarchy would have included multiple 'tiled' layers, complicating the structure.

![image](https://github.com/user-attachments/assets/1f57a467-8359-4251-b97b-120ef7abbe90)

*Image 6. Item Hierarchy 1*


![image](https://github.com/user-attachments/assets/698f2a3a-44c7-4c0b-b595-bf81ad913a60)

*Image 7. Item Hierarchy 2*

The final container structure is below. Our primary floating vertical container comprises of the orange border, whilst the 3 horizontal containers within this container are shaded blue. 

![image](https://github.com/user-attachments/assets/132ea26b-8cd0-4097-9a07-e2d421d1ecaf)

*Image 8. Container Structure*

## Final Sales Dashboard

After formatting and re-arranging the elements, below is the final version of the Sales Dashboard.

![image](https://github.com/user-attachments/assets/11bad169-b104-41b2-ab20-9aa64c7eb4d3)

*Image 9. Sales Dashboard 1*

![image](https://github.com/user-attachments/assets/b75e0eff-0801-444a-b044-77cd9dbee457)

*Image 10. Sales Dashboard 2*

Key points regarding the Sales Dashboard:
- The years displayed on the dashboard are all dynamic and update automatically based on the user's selected year. As illustrated in Image 10, the years have changed to 2021 for the current year and 2020 for the previous year. By keeping the years visible on the screen at all times, end users can easily see the relevant time periods without having to refer back to the filter. 
- A clear visual hierarchy is visible with the KPI's prominently displayed at the top
- Whitespace has been utilised to divide the dashboard into distinct sections, preventing clutter and making the overall layout more visually appealing and easier on the eye.
- Contrasting colours have been used to highlight different elements, such as low and high months, making them easier to distinguish. Additionally, the colours serve as codes to build familiarity: orange for loss/lower values and blue for profit/higher values. This allows for quicker comprehension. When readers first associate orange with loss in the BANs, they will immediately recognise that anything marked with orange in the sales and profit by subcategory chart and the sales and profit trends over time chart indicates lower values. This also maintains consistency through the dashboard.
- The navigation icons change from blue to white and vice versa depending on which dashboard the end user is viewing, providing a clear visual indicator of the end user's current location within the dashboard.
- The filter pane can be kept on display or hidden using the 'x' button, this optimises screen space and potentially improves loading times by reducing the number of visible elements on the screen at once.

# Requirements Analysis (Customers Dashboard)

## Content Requirements

The requirements below for the Customers Dashboard have also been provided to us by management.

**KPI Overview:**

- Display a high level view of the total number of customers, total sales per customer and the total number of orders for the current and previous years.

**Customer Trends:**
- Present data for each KPI on a monthly basis for the current and previous year.
- Identify the months with the highest and lowest sales, highlighting these months for easier recognition. 

**Customer Distribution by Number of Orders:**
- Provide a representation of the distribution of customers based on the number of orders placed to provide insights into customer behaviour, loyality and engagement. 

**Top 10 Customers by Profit:**
- Display the top 10 customers by profits in descending order.
- Show additional information such as rank, number of orders, current sales, current profit and the last order date.

## Design Requirements

- Allow the end user flexibiity to view historical data.
- Allow the end user easy navigatation between dashboards.
- Interactive charts, allowing end users to filter data using the charts.
- The dashboard should allow end users to filter by category, subcategory and location (region, state and city).

## ## Strategy to Meet Content and Design Requirements

Below is our plan to meet the content and design requirements.

**KPI Overview:**

- **Display a high level view of the total number of customers, total sales per customer and the total number of orders for the current and previous years.**

**Customer Trends:**
- **Present data for each KPI on a monthly basis for the current and previous year.**
- **Identify the months with the highest and lowest sales, highlighting these months for easier recognition.**

The KPI Overview and Customer Trend requirements are very similar to the KPI requirements and Sales Trends for the Sales Dashboard above. Hence, the approach to meet these requirements will be exactly the same. BAN's will be used to display the KPI's whilst sparklines will be used to showcase customer trends overtime. 

**Customer Distribution by Number of Orders:**

- **Provide a representation of the distribution of customers based on the number of orders placed to provide insights into customer behaviour, loyalty and engagement.**

Whenever "distribution" is mentioned in a requirement, **histograms** are the first type of chart that come to mind. A **histogram** helps in understanding the frequency distribution of customers across different ranges (bins) of the number of orders placed, providing a clear visualisation of the overall distribution. Additionally, histograms enable the identification of outliers or unusual data points, which may indicate unique customer segments or behaviours." 

**Top 10 Customers by Profit:**
- **Display the top 10 customers by profits in descending order.**
- **Show additional information such as rank, number of orders, current sales, current profit and the last order date.**

For Top 10 Customers by Profit, a simple **table** will be used. Due to the amount of detail we have to display, a table with the metrics as columns and ranks as rows will provide a clear picture of the information required. 

Parameters will be employed to enable end users to access historical data from previous years. For interactivity, dimension, date, and action filters will be implemented, allowing end users to filter data via the charts, as well as by category, subcategory, and location. Additionally, navigation buttons will be incorporated to facilitate easy navigation between dashboards.

We will not create a mockup for the Customer Dashboard, as it will be the exact same structure as the Sales Dashboard. We will also skip Data Source Preparation as we already have the data source prepared.

# Building Charts

## BANs

We will follow the exact same process here as we did for the Sales Dashboard, which is to create the required calculated fields, test these fields and test/validate the aggregated values using Excel. 

## Sparklines

The same process as the Sales Dashboard will be followed here too.

## Histogram and Weekly Trends for Sales and Top 10 Customers by Profit

To show the customer distribution, since we are talking aboout two measures 1) Count of customers and 2) Count of orders, we have to use an LOD (level of detail) expression to generate the bins for the histogram and find the total number of orders for each customer for the current year. The LOD expression used is below.

```
{ FIXED [CY Customers]: COUNTD([CY Orders])}

```

Basically, this LOD expression is telling Tableau to fix the calculation at the current year customers level, and to count the number of unique orders for each customer. The result will be the number of unique orders placed by each customer. 

For the Top Customers by Profit table, we used the INDEX() function to assign a rank to the rows. The default table were also removed and replaced with custom headers using text objects within a horizontal container. 


# Building Dashboard

## Final Customers Dashboard

The sizing and container structure will be exactly the same as the Sales Dashboard. The only primary differences between the two dashboard are the different charts.

After formatting and re-arranging the elements, below is the final version of the Customers Dashboard.

![image](https://github.com/user-attachments/assets/3a4c4d59-995c-4712-9922-f1a977306100)

*Image 11. Customers Dashboard*

# Insights Analysis

We can now go ahead and utilise our developed dashboards to derive key insights. As analysts, our role extends beyond merely creating dashboards. Our primary role is to apply our analytical skills to interpret the key information conveyed by the data and effectively communicating these insights to stakeholders

**Total Sales**

- In 2023, total sales were $733K, which were 20.4% higher than total sales in 2022.
- The lowest month of total sales in 2023 was February with $20K in total sales, whilst the highest month of total sales in 2023 was November with $118k in total sales.
- There are dips and rises in sales throughout 2023, and this is also visible for the years prior to 2020. There are several commonalities between the sales trends from 2020 to 2023. February was the lowest selling month in 2020, 2021 and 2023, whilst January was the lowest selling month in 2022. January and February are the lowest selling months, and this may simply be due to the fact that after Christmas and New Years retail spending slows down as the festive season is over and people tend to leave for holidays including businesses.
- Another commonality that can be seen across all years is a steady sales trend till July and August, followed by a spike in sales in September, with sales hitting a peak prior and during the Christmas festive season in the months of November and December. An exception here was in 2020, where sales peaked in September. The spike in sales in the month of September can be due to several reasons such as back to school shopping with Summer break coming to an end, end of Summer sales and Labor Day (celebrated on the first Monday of September) sales. September may have been the peak sales month in 2020, as opposed to November or December which are normally the peak sales months, due to Covid and with many states going to re-opening phases around September, which may have led to more consumer spending.
- Overall, total sales are on an upward trend, with increases from the year before since 2020. In 2020 sales were $484K, with sales reaching $733K in 2023, this is a 51.45% increase over 3 years.

**Total Profit**

- In 2023, total profit was $93K, which was 14.2% higher than total profit in 2022.
- The lowest month of profitability in 2023 was April ($1K Profit), whilst the highest month of profitability in 2023 was March ($15K).
- Like total sales, there are dips and rises in profitabilty throughout 2023, and this is also visible for the years prior to 2020. There are differences between profitability trends from 2020 to 2023. In 2020 the lowest and highest months of profitability were July and November respectively, with the lowest month of profitabillity changing to January in 2021 and finally, the lowest and highest months of profitability changing to August and December respectively in 2022. The reason why November-December tend to be the peak months of profitability may simply be due to to increased spending around the Christmas festive season. The month of March being the highest month of profitability in 2023 is interesting, even higher than the festive season months and warrants further investigation. Was it due to higher profitability products being sold more in that month? Why? Was it due to the release of a flagship phone in that month or a high in demand product?
- Overall, total profitability is on an upward trend too like sales, with increases from the year before since 2020. In 2020, total profit was $50K, with total profit reaching $93K in 2023, this is a 86% increase over 3 years. 

**Total Quantity**

- In 2023, total quanity of units sold was 12K, which was 26.8% higher than the total quantity sold in 2022.
- The lowest selling month of units 2023 was February (363 units), whilst the highest month of sellling units was in 2023 was November with 1840 units sold. 
- Like total sales and profit, there are dips and rises in total units sold throughout 2023, and this is also visible for the years prior to 2020. There are commonalities between unit selling trends from 2020 to 2023, with January-February being the lowest unit selling months and November-December being the highest unit selling months. This may also be simply due to the fact that spending and purchases increase around the festive months and decrease right after the festive months are over in January and February.
- The total quantity of units sold trends from 2020 to 2023 resemble the total sales trends quite closely, with steady units sold until July-August and a spike in September. 
- Overall, total profitability is on an upward trend too like sales and profit, with increases from the year before since 2020. In 2020, total quantity sold was $8K, with total quantity sold reaching 12K in 2023, this is a 50% over 3 years. 

**Sales and Profit by Subcategory**

- From 2020 to 2023, phones and chairs subcategories have generated the most sales, whilst copiers, accessories and phones tend to be the higher profitability subcategories. 
- Subcategories with lower sales than the previous year tend to change, with 8 subcategories in 2021 with lower sales compared to 2020, reducing to 3 categories with lower sales in 2022 compard to 2021 and then 3 different categories to 2022, with sales lower in 2023 compared to 2022.
- Subcategories such as tables have not been profitable from 2020 to 2023, which warrants further investigation as to why this is the case. Have there been increased discounts offered on table sales?

**Sales and Profit Trends over Time** 

*Analysis to be continued*




