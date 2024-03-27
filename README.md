# python-challenge-1
# Module 2 Challenge

This Python script simulates an ordering system for a variety food truck. Customers can select items from different categories, specify quantities, and review their orders. Here's a breakdown of the functionalities:

## Menu Dictionary

The script contains a dictionary named `menu` which represents the food truck's menu. It's structured with various categories such as Snacks, Meals, Drinks, and Desserts, each containing a variety of items with their corresponding prices.

## Ordering Process

1. **Order List Setup**: An empty list named `customers_order` is created to store the customer's order details.
2. **Order Placement**: The script launches with a greeting and prompts customers to order items continuously until they're done.
3. **Menu Selection**: Customers are asked to select a menu category from the available options.
4. **Item Selection**: After choosing a category, customers select a specific item by its number.
5. **Quantity Selection**: Customers specify the quantity of the selected item they wish to order.
6. **Order Confirmation**: Customers can continue ordering or finish their order.
7. **Order Review**: Once the order is complete, the script displays the items ordered along with their prices and quantities.
8. **Total Cost Calculation**: The total cost of the order is calculated and displayed.

## How to Use

To use this script:
- Run the Python script.
- Follow the prompts to select items from the menu, specify quantities, and review your order.
- Once you're done ordering, the script will display a summary of your order including the total cost.

## Example Usage

# Run the script and follow the prompts
# Example output:
# Welcome to the variety food truck.
# From which menu would you like to order?
# 1: Snacks
# 2: Meals
# 3: Drinks
# 4: Dessert
# Type menu number: 2
# You selected Meals
# What Meals item would you like to order?
# Item # | Item name                | Price
# -------|--------------------------|-------
# 1      | Burrito                  | $4.49
# 2      | Teriyaki Chicken         | $9.99
# ...
# Please type the number you would like: 1
# How many Burrito(s) would you like to order? 2
# Would you like to keep ordering? (Y)es or (N)o y
# ...
# This is what we are preparing for you.
# ...
# Total cost of the order: $15.46

