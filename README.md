Day 10 Restaurant Order Analysis (MongoDB)

Project Overview
Created a restaurant order database using MongoDB Compass. Analyzed popular menu items, revenue by category, peak hours, top customers, and daily revenue trends.

Database Setup

Database Name: restaurant_db
Collections:
- menu_items (8 documents)
- customers (5 documents)
- orders (10 documents)

Collection Structures

menu_items:
{
  item_id: Integer,
  item_name: String,
  category: String,
  price: Integer,
  cost: Integer
}

customers:
{
  customer_id: Integer,
  customer_name: String,
  phone: String,
  city: String
}

orders:
{
  order_id: Integer,
  customer_id: Integer,
  order_date: String,
  order_time: String,
  items: Array,
  total_amount: Integer,
  payment_method: String
}

Aggregation Queries and Results

Query 1: Most Popular Items (Top 5 by quantity sold)
Pipeline: $unwind -> $group -> $sort -> $limit

Results:
Margherita Pizza: 5 quantities
Pepperoni Pizza: 3 quantities
Chicken Wings: 2 quantities
Garlic Bread: 3 quantities
Tiramisu: 3 quantities

Query 2: Revenue by Category
Pipeline: $unwind -> $lookup -> $unwind -> $group -> $sort

Results:
Pizza: 2,500
Appetizer: 600
Main Course: 700
Dessert: 450
Beverage: 250
Salad: 200

Query 3: Peak Hours Analysis
Pipeline: $group -> $sort

Results:
19:00-20:00: 4 orders (Highest)
20:00-21:00: 3 orders
13:00-14:00: 1 order
14:00-15:00: 1 order
21:00-22:00: 1 order

Query 4: Top Customers by Spending
Pipeline: $group -> $sort -> $limit

Results:
Rajesh: 3 orders, Total 1,341
Vikram: 1 order, Total 1,047
Priya: 2 orders, Total 997
Neha: 2 orders, Total 995
Amit: 2 orders, Total 895

Query 5: Daily Revenue Trend
Pipeline: $group -> $sort

Results:
2024-01-15: 1,345
2024-01-16: 846
2024-01-17: 1,444
2024-01-18: 696
2024-01-19: 944

Skills Demonstrated
- MongoDB database and collection creation
- Document insertion
- $unwind stage for array fields
- $lookup stage for joining collections
- $group stage with $sum, $multiply
- $sort and $limit stages
- Date and time string manipulation

Files Included
- restaurant_queries.json: Complete MongoDB aggregation queries
- Screenshots folder: All query results

Created
May 2024

Author
Abhishek C D
