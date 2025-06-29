-- 1. Total Sales by Country
SELECT COUNTRY, SUM(SALES) AS Total_Sales
FROM sales_data
GROUP BY COUNTRY
ORDER BY Total_Sales DESC;

-- 2. Monthly Sales Trend
SELECT MONTH_ID, SUM(SALES) AS Monthly_Sales
FROM sales_data
GROUP BY MONTH_ID
ORDER BY MONTH_ID;

-- 3. Top 5 Customers by Total Sales
SELECT CUSTOMERNAME, SUM(SALES) AS Total_Sales
FROM sales_data
GROUP BY CUSTOMERNAME
ORDER BY Total_Sales DESC
LIMIT 5;

-- 4. Average Price by Product Line
SELECT PRODUCTLINE, AVG(PRICEEACH) AS Avg_Price
FROM sales_data
GROUP BY PRODUCTLINE;

-- 5. Orders with Sales Above $10,000
SELECT ORDERNUMBER, SALES, CUSTOMERNAME
FROM sales_data
WHERE SALES > 10000
ORDER BY SALES DESC;

-- 6. Total Orders by Year and Deal Size
SELECT YEAR_ID, DEALSIZE, COUNT(*) AS Order_Count
FROM sales_data
GROUP BY YEAR_ID, DEALSIZE
ORDER BY YEAR_ID, DEALSIZE;

-- 7. Inner Join Example (Assumes a 'product_info' table exists)
SELECT s.PRODUCTLINE, p.PRODUCTNAME, s.SALES
FROM sales_data s
JOIN product_info p ON s.PRODUCTCODE = p.PRODUCTCODE;
