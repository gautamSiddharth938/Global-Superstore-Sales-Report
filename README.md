
# Global Superstore Sales Report

### Dashboard Link : https://app.powerbi.com/groups/me/reports/14ce58af-9297-497e-9eb5-5e6fb0050cab/5710996b7ccda411ea50?experience=power-bi

## Problem Statement

The objective of this project is to analyze the sales performance of Global Superstore, identify key trends, and provide actionable insights to improve overall business performance. The sales report will focus on understanding the sales distribution, profit margins, shipping costs, and other critical metrics across different regions, product categories, and customer segments.

Global Superstore operates in multiple regions, offering a wide range of products. The store aims to optimize its sales strategy, enhance profitability, and reduce shipping costs while maintaining high customer satisfaction. With a diverse product portfolio and varying market dynamics across regions, it is crucial to leverage data-driven insights to make informed business decisions.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.  
- Step 5 : A new Calculated column was added to the table in the Table View named as COGS(Cost of Goods Sold) to calculate cost of goods sold.

for creating new column following DAX expression was written;

        COGS = superstore[Sales] - (superstore[Profit] + superstore[Shipping.Cost])
- Step 6 : New Calculated column was added to the table named as Unit Price to calculate Unit price of product.

for creating new column following DAX expression was written;

        Unit Price = superstore[Sales] / superstore[Quantity]       
- Step 7 : Measure table was created to store measures and new measure was created to find All Segments.

Following DAX expression was written for the same,
        
        All Segments = DISTINCT(superstore[Segment])
- Step 8 : New measure was created to find  Total Customers,
 
 Following DAX expression was written to find Total Customers,
 
        Total Customers = DISTINCTCOUNT(superstore[Customer.ID])
- Step 9 : New measure was created to calculate Total Sales.
 
 Following DAX expression was written to find Total Sales,
 
         Total Sales = SUM(superstore[Sales])
- Step 10 : New measure was created to calculate Total Shipping Cost.
 
 Following DAX expression was written to find Total Shipping Cost,
 
         Total Shipping Cost = SUM(superstore[Shipping.Cost])
- Step 11 : New measure was created to calculate Total Unit Price.
 
 Following DAX expression was written to find Total Unit Price,
 
         Total Unit Price = SUM(superstore[Unit Price]) 
- Step 12 : New measure was created to calculate Total Discount.
 
 Following DAX expression was written to find Total Discount,
 
        Total Discount = SUM(superstore[Discount])
- Step 13 : New measure was created to calculate Total Orders.
 
 Following DAX expression was written to find Total Orders,
 
        Total Orders = DISTINCTCOUNT(superstore[Order.ID])
- Step 14 : New measure was created to calculate Total Profit.
 
 Following DAX expression was written to find Total Profit,
 
        Total Profit = SUM(superstore[Profit])  
- Step 15 : New measure was created to calculate Total Quantity Sold.
 
 Following DAX expression was written to find Total Quantity Sold,
 
        Total Quantity Sold = SUM(superstore[Quantity])
- Step 16 : New measure was created to calculate Average Profit Per Order.
 
 Following DAX expression was written to find Average Profit Per Order,
 
        Average Profit Per Order = AVERAGE(superstore[Profit]) 
- Step 17 : New measure was created to calculate % of Average Sales Per Order.
 
 Following DAX expression was written to find % of Average Sales Per Order,
 
        Average Sales per Order = AVERAGE(superstore[Sales])    
- Step 18 : New measure was created to calculate Profit Margin.
 
 Following DAX expression was written to find Profit Margin,
 
        Profit Margin = DIVIDE(
    [Total Profit], [Total Sales])
- Step 19 : New measure was created to calculate Sales to Shipping Cost Ratio.
 
 Following DAX expression was written to find Sales to Shipping Cost Ratio,
 
        Sales to Shipping Cost Ratio = DIVIDE(
    [Total Sales], 
    [Total Shipping Cost])  
- Step 20 : New measure was created to calculate BJP Total Cost.
 
 Following DAX expression was written to find BJP Total Cost,
 
        Total Cost = [Total Sales] + [Total Shipping Cost]
- Step 21 : New measure was created to calculate Profit Per Unit.
 
 Following DAX expression was written to find Profit Per Unit,
 
        Profit Per Unit = DIVIDE([Total Profit], [Total Quantity Sold], 0)     
- Step 22 : New measure was created to calculate Cost Per Unit.
 
 Following DAX expression was written to find Cost Per Unit,
 
        Cost Per Unit = DIVIDE([Total Cost], [Total Quantity Sold], 0)                               
- Step 23 : In the report view, under the view tab, theme was selected.
- Step 24 : Four card visuals were added to the canvas in overview page, one representing Total Sales, next one representing Total Profit followed by Total Quantity Sold and Total Shipping cost respectively. Also logo been inserted on the top left corner of the page.
           A line Graph was added below cards on left representing Sales and Profit By Categories and sub-categories. Another Line graph were added below previous line graph representing Profit Margins by Year.
           Two Donut Charts were added representing Orders by Category & Segment. Below that a matrix representing top 10 Products by total Sales(product -name, Orders, Sales and Profit).
- Step 25 : Another page been added and map were inserted to represent country heirarchy by Total Profit. Moreover a slicer been added of countries. 
- Step 26 : Three card visuals were added to the canvas in new page named Customer Details, representing Top customer by Sales with its order and sales.
          Below Cards Two donut charts were added representing Sales by Region amd Market.
          On the right of the page a line graph were added representing Sales by Category and sub-Category. Below that a matrix were added to show Top 20 Customers by Total Profit(Customer-name, Unit Price, Cost Per Unit, Orders, Shopping Cost, Cost, Profit per Unit, Profit Margin, Sales).  
- Step 27 : Also Navigation bar were added with filter , overview, map, and Customer Details button on all 3 pages to make navigation possible between all pages.
- Step 28 : The report was then published to Power BI Service.
 
 
![Screenshot 2024-07-25 214020](https://github.com/user-attachments/assets/867fad9d-2d7a-4908-920f-f89b5f75399f)

# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo]![Screenshot 2024-07-26 102218](https://github.com/user-attachments/assets/a8ad7e99-97a1-46a2-a7bb-f1780088be55)

![Screenshot 2024-07-26 102250](https://github.com/user-attachments/assets/b547ecb5-6835-4dcf-b62b-81362ef6f2e4)

 
 # Report Snapshot (Power BI DESKTOP)

![Dashboard_upload] ![Opera Snapshot_2024-07-27_154223_app powerbi com](https://github.com/user-attachments/assets/a543b187-a457-420d-990f-c5fb7104b48e)

![Opera Snapshot_2024-07-26_102632_app powerbi com](https://github.com/user-attachments/assets/7a6c09e2-f863-48ef-a6f0-aea05ffd80e3)

# Insights

A Dual page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Categories = 3

    Total Sub-categories = 17
    Total Products = 10,292
    Total Customers = 795
    Total Orders = 25,035
    Total Order-priority = 4
    Total Segment = 3
    Total Ship-mode = 4
    Total Countries = 147
    Total Cities = 3,636
    Total Profit = $1,467,457.29
    Total Sales = $1,26,42,905

    Some Totals while creating report of sales can be seen easily.
           
### [2] Some Stats

    a) Most Odered Product - Staples
    b) Least Odered Product - 4009 Highlighters
    c) Most Profitable Product - Canon imageCLASS 2200 Advanced Copier
    d) Least Profitable Product - Cubify CubeX 3D Printer Double Head Print
    e) Product with Highest Sales - Apple Smart Phone, Full Size
    f) Product with Lowest Sales - Eureka Disposable Bags for Sanitaire Vibra Groomer I Upright Vac
    g) Product with most quantity sold and customers - Staples
    h) Product with Least quantity sold and customers - Boston 1900 Electric Pencil Sharpener
    i) Product with Highest shipping cost - Motorola Smart Phone, Full Size
    j) Product with Lowest shipping cost - Eureka Disposable Bags for Sanitaire Vibra Groomer I Upright Vac
    k) Country with Highest Profit earned - United States
    l) Country with Lowest Profit earned - Turkey
    m) Country with Most Customers - United States
    n) Country with Least Customers - Bahrain
    o) Country with High Shipping Cost - United States
    p) Country with low Shipping Cost - Eritrea
    q) Country with Most Sales - United States
    r) Country with Lowest Sales - Equatorial Guinea
    s) Product with Highest Cost - Apple Smart Phone, Full Size
    t) Product with Lowest Cost - Eureka Disposable Bags for Sanitaire Vibra Groomer I Upright Vac
    u) Product with high Profit margin - Xerox 20
    v) Product with low Profit margin - Chromcraft Training Table, Adjustable Height

  while Creating Measures and dashboard few stats which can be important. 
  
