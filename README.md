# Sales-Analysis-Project
This project aims to analyze the sales performance of various electronics products using SQL. The data used in this project is dummy data created for learning and demonstration purposes. The project showcases the ability to design a database, write SQL queries, and derive meaningful insights from sales data.
--#Analyzing Sales Performance of Electronics Products

create table sales (
    order_id int primary key,
    product_id int,
    quality_id int,
    price DECIMAL(10,2),
    Product_name VARCHAR(50));

    insert into sales (order_id, product_id, quality_id, price, product_name)
    VALUES
    (1, 101, 201, 999, '32" HD ready smart LED TV'),
    (2, 102, 202, 20499, '1.5 ton 5 star split AC'),
    (3, 103, 203, 1999, 'Microwave Oven'),
    (4, 104, 204, 39999, 'Refrigerator'), 
    (5, 105, 205, 59999, 'Washing Machine'), 
    (6, 106, 206, 24999, 'Dishwasher'), 
    (7, 107, 207, 14999, 'Vacuum Cleaner'),
     (8, 108, 208, 44999, 'Laptop'), 
     (9, 109, 209, 34999, 'Tablet'), 
     (10, 110, 210, 54999, 'Smartphone'), 
     (11, 111, 211, 21999, 'Home Theater System'),
      (12, 112, 212, 26999, 'Gaming Console'), 
      (13, 113, 213, 31999, 'Smart Watch'), 
      (14, 114, 214, 41999, 'Digital Camera'), 
      (15, 115, 215, 51999, 'Printer'), 
      (16, 116, 216, 61999, 'Scanner'), 
      (17, 117, 217, 27999, 'Monitor'),
     (18, 118, 218, 32999, 'Keyboard'), 
     (19, 119, 219, 42999, 'Mouse'), 
     (20, 120, 220, 52999, 'Speaker');

     select*from sales

--Total_Sales for Each Product

     select product_name, sum(price) AS total_sales
     from sales
     group by product_name
     order by total_sales DESC; 

--total sales amount
     SELECT SUM(price) AS total_sales_amount
FROM sales;

--average sales price per product
SELECT product_name, AVG(price) AS average_price
FROM sales
GROUP BY product_name
ORDER BY average_price DESC;

--total quantity sold for each product
SELECT product_name, COUNT(order_id) AS total_quantity_sold
FROM sales
GROUP BY product_name
ORDER BY total_quantity_sold DESC;

--Products with Sales Above a Certain Amount
select product_name, sum(price) AS total_sales
from sales
group by product_name
having sum(price)>20000
order by total_sales DESC;

--Highest and Lowest Sales Price
select max(price) AS highest_price, MIN(price) AS lowest_price
FROM sales;

--Total Sales for Each Order
select order_id, sum(price) AS Total_sales
From sales
group by order_id
order by total_sales DESC;





