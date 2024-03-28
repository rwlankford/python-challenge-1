# python-challenge-1
# Module 2 Challenge

This `menu.py` Python script simulates an ordering system for a variety food truck. Customers can select items from different categories, specify quantities, and review their orders. Here's a breakdown of the functionalities:

## Menu Dictionary

The script contains a dictionary named `menu` which represents the food truck's menu. It's structured with various categories such as Snacks, Meals, Drinks, and Desserts, each containing a variety of items with their corresponding prices.

## Ordering Process

1. **Order List Setup**: An empty list named `customers_order` is created to store the customer's order details.
```python
customers_order = []
```
A loop is created to allow the customer to continue ordering as long as `place_order` is equal to `True`
```python
place_order = True
```
2. **Order Placement**: The script launches with a greeting and prompts customers to chose the menu from which they would like to order.  This input is stored in the `menu_items` dictionary for later retrieval and the corresponding menu category is stored and  printed to the screen
```python
menu_items = {}

for key in menu.keys():
  print(f"{i}: {key}")
  menu_items[i] = key
```
3. **Menu Selection**: Customers are asked to select a menu category from the available options which is converted to an integer and stored as `menu_selection` checked against the `menu_items` dictionary and stored as the variable `item_name`
```python
menu_selection = input("Please type the number you would like: ")

if menu_selection.isdigit():
menu_selection = int(menu_selection)

if menu_selection in menu_items.keys():
item_name = menu_items[menu_selection]["Item name"]
```  
4. **Item Selection**: After choosing a category, customers select a specific item by its number which is stored as `menu_selection`.  The `menu_selection` is then confirmed to be a number and converted to an integer.  `menu_selection` is then check against the keys in the `menu_items` dictionary and stored as `item_name`
```python
menu_selection = input("Please type the number you would like: ")

if menu_selection.isdigit():
  menu_selection = int(menu_selection)

if menu_selection in menu_items.keys():
  item_name = menu_items[menu_selection]["Item name"]
```
5. **Quantity Selection**: Customers specify the `quantity` of the selected item they wish to order which is confirmed to be a number and stored as an integer. If it is not a number an error is returned and the `quantity` is set to `1` by default.
```python
quantity = input(f"How many {item_name}s would you like to order? ")

if quantity.isdigit():
  quantity=int(quantity)
else:
print(f'{quantity} is an invalid entry.  Only one item will be selected')
quantity=1
```  
6. **Add to Order**: Customers selection and `quantity` are added to the `customers_order`.
```python
customers_order.append({
"Item name": menu_items[menu_selection]["Item name"],
"Price": menu_items[menu_selection]["Price"],
"Quantity": quantity
})
```     
7. **Order Confirmation**: Customers are asked if they would like to continue ordering or finish their order.  Their input is required to be characters `Y/y` or `N/n` and stored as the varialbe `keep_ordering`.  The input is then check to ensure it the proper characters and then converted to lowercase to ensure consistency.  If the user is finished ordering `place_order` is set to `False` and the user is thanked for their order.  If the user entered invalid characters they are asked to re-enter.
```python
keep_ordering = input("Would you like to keep ordering? (Y)es or (N)o ")

if keep_ordering.lower() == 'y':
  break

elif keep_ordering.lower() == 'n':
  place_order = False
  print("Thank you for your order!")
  break 

else:
  print("Invalid input. Please enter 'Y' or 'N'.")
```
8. **Order Review**: Once the order is complete the script converts and stores the `items` in `customer_order` to variables, calculates the length of each variable for spacing and displays the `item_name` ordered along with their `price` and `quantitiy`.
```python
for items in customers_order:
    item_name = items["Item name"]
    price = items["Price"]
    quantity = items["Quantity"]

    item_name_length = len(item_name)
    price_length = len(str(price))
    quantity_length = len(str(quantity))

    item_name_spaces = " " * (26 - item_name_length)
    price_spaces = " " * (6 - price_length)  
    quantity_spaces = " " * (10 - quantity_length) 

    print(f"{item_name}{item_name_spaces}| ${price}{price_spaces}| {quantity}{quantity_spaces}")
```
9. **Total Cost Calculation**: The 'total_cost` of the order is calculated and displayed.
```python
total_cost = sum(item["Price"] * item["Quantity"] for item in customers_order)
```

## How to Use

To use this script:
- Run the Python script.
- Follow the prompts to select items from the menu, specify quantities, and review your order.
- Once you're done ordering, the script will display a summary of your order including the total cost.

## Example Usage

Output of the script should look as follows:

Welcome to the variety food truck.

From which menu would you like to order?
1. Snacks
2. Meals
3. Drinks
4. Dessert

```
User Inputs:  2 (Meals) 
```

You selected Meals

What Meals item would you like to order?

Item # | Item name                | Price  
-------|--------------------------|-------  
1      | Burrito                  | $4.49  
2      | Teriyaki Chicken         | $9.99  
...

Please type the number you would like:

```
User Inputs: 1 (Burrito)
```
How many <item name>s would you like to order?  
```
User Inputs: 1  
```
Would you like to keep ordering? (Y)es or (N)o  
```
User Inputs: N
```
This is what we are preparing for you.  

Item name                 | Price  | Quantity  
--------------------------|--------|----------  
Burrito                   | $4.49  |     1  

Total cost of the order: $4.49  
  
  
## Credits 
This code was written by [Richard Lankford](https://github.com/rwlankford/python-challenge-1/tree/main) with assistance and review from **Rimi Sharma** and **Tyler B. Shubert**





