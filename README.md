Objective

The objective of this assignment is to perform DAX calculations and build interactive Power BI visualizations to analyze sales performance, profitability, order distribution, and regional sales trends.

Part A – DAX Calculations
1. Calculated Columns
Task 1: Category Type

Objective: Create a calculated column in the Order Details table by combining the Category and Sub-Category columns into a single field named Category Type.

Formula

Category Type = 'Order Details'[Category] & " - " & 'Order Details'[Sub-Category]
Task 2: Revenue per Order

Objective: Create a calculated column to calculate the revenue generated for each order.

Formula

Revenue = 'Order Details'[Amount] * 'Order Details'[Quantity]
Task 3: Sales Category

Objective: Create a calculated column that classifies each order as Above Average or Below Average based on the Amount.

Formula

Sales Category =
IF(
    'Order Details'[Amount] >
    AVERAGE('Order Details'[Amount]),
    "Above Average",
    "Below Average"
)
Part B – DAX Measures
1. Order Count

Objective: Calculate the total number of orders.

Formula

Order Count = COUNT('Order Details'[Order ID])
2. Average Profit in Delhi

Objective: Calculate the average profit for orders placed in Delhi.

Formula

Average Profit in Delhi =
CALCULATE(
    AVERAGE('Order Details'[Profit]),
    'List of Orders'[City] = "Delhi"
)
3. Year-to-Date (YTD) Sales

Objective: Calculate cumulative sales from the beginning of the year up to the current date.

Formula

YTD Sales =
TOTALYTD(
    SUM('Order Details'[Amount]),
    'List of Orders'[Order Date]
)
Part C – Data Visualization
1. Sales Target Achievement by Category

Visualization: Clustered Column Chart

Fields

Axis → Category
Values → Sum of Amount
Values → Sum of Target
2. Max Profit Margin by Sub-Category

Visualization: Donut Chart

Fields

Legend → Sub-Category
Values → Maximum of Profit Margin
3. Monthly Sales Trend

Visualization: Line Chart

Fields

X-Axis → Month (Order Date)
Y-Axis → Sum of Amount
4. Comparison of Profit and Quantity by Sub-Category

Visualization: Scatter Chart

Fields

X-Axis → Quantity
Y-Axis → Profit
Details → Sub-Category
5. Comparison of Total Sales Amount and Target
Card 1
Value → Sum of Amount
Card 2
Value → Sum of Target
Multi-row Card
Category → Segment
Value → Minimum Target
6. Sales Performance Matrix

Visualization: Matrix

Fields

Rows → Category
Columns → Month
Values → Sum of Amount
Values → Sum of Target
7. Geographic Sales Analysis

Visualization: Map (or Azure Maps)

Fields

Location → City
Bubble Size → Sum of Amount
Tooltips → State, Profit
8. Sales Distribution by Sub-Category

Visualization: Treemap

Fields

Category (or Group) → Sub-Category
Values → Sum of Amount
9. Order Count Analysis by State

Visualization: Funnel Chart

Fields

Category → State
Values → Count of Order ID

Sort the chart in Descending order by Count of Order ID.
Expected Learning Outcomes

After completing this assignment, you will be able to:

Create calculated columns using DAX.
Develop measures for business analysis.
Build interactive Power BI dashboards.
Analyze sales, profit, and order trends.
Compare actual sales against targets.
Visualize geographical sales performance.
Interpret business insights using different Power BI visuals.
