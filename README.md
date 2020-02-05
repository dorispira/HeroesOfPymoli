## Heroes of Pymoli

Congratulations! After a lot of hard work in the data munging mines, you've landed a job as Lead Analyst for an independent gaming company. You've been assigned the task of analyzing the data for their most recent fantasy game Heroes of Pymoli.

Like many others in its genre, the game is free-to-play, but players are encouraged to purchase optional items that enhance their playing experience. As a first task, the company would like you to generate a report that breaks down the game's purchasing data into meaningful insights.

-----
## Objectives

Your final report should include each of the following:

### Player Count

* Total Number of Players

```python
# Total Number of Players in a dataframe
number_of_players = len(purchase_data["SN"].value_counts())
player_count = pd.DataFrame([number_of_players], columns = ["Total Players"])
player_count
```

### Purchasing Analysis (Total)

* Number of Unique Items
* Average Purchase Price
* Total Number of Purchases
* Total Revenue

```python
# Count number of unique items
unique_items = len(purchase_data["Item Name"].unique())
unique_items

# Calculate average price
avg_price = "${:.2f}".format(purchase_data["Price"].mean())
avg_price

# Count number of purchases
number_of_purchases = len(purchase_data["Purchase ID"].unique())
number_of_purchases

# Calculate total revenue
total_revenue = "${:.2f}".format(purchase_data["Price"].sum())
total_revenue

# Organize my DatFrame

purchase_summary = {'Average Price': avg_price,
                    'Number of Purchases': number_of_purchases,
                    'Number of Unique Items': unique_items,
                    'Total Revenue': total_revenue}

purchase_summary_df = pd.DataFrame([purchase_summary], columns = ["Number of Unique Items", 
                                                                  "Average Price", 
                                                                  "Number of Purchases", 
                                                                  "Total Revenue"])
purchase_summary_df
```

### Gender Demographics

* Percentage and Count of Male Players
* Percentage and Count of Female Players
* Percentage and Count of Other / Non-Disclosed

### Purchasing Analysis (Gender)

* The below each broken by gender
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value
  * Average Purchase Total per Person by Gender

### Age Demographics

* The below each broken into bins of 4 years (i.e. &lt;10, 10-14, 15-19, etc.)
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value
  * Average Purchase Total per Person by Age Group

### Top Spenders

* Identify the the top 5 spenders in the game by total purchase value, then list (in a table):
  * SN
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value

### Most Popular Items

* Identify the 5 most popular items by purchase count, then list (in a table):
  * Item ID
  * Item Name
  * Purchase Count
  * Item Price
  * Total Purchase Value

### Most Profitable Items

* Identify the 5 most profitable items by total purchase value, then list (in a table):
  * Item ID
  * Item Name
  * Purchase Count
  * Item Price
  * Total Purchase Value
