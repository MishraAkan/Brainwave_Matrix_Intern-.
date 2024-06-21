##Data Collection and Preparation..

'''We'll assume we have the following sales data for a store:

Order ID: Unique identifier for each transaction.
Date: Date of the transaction.
Customer ID: Unique identifier for each customer.
Product ID: Unique identifier for each product.
Product Category: Category to which the product belongs.
Quantity Sold: Number of units sold in the transaction.
Price: Price per unit of the product.'''

import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Generate the commercial data..
np.random.seed(42)
dates = pd.date_range(start='2023-01-01', end='2023-12-31', freq='D')
num_records = 1000
data = {
    'OrderID': np.arange(1, num_records + 1),
    'Date': np.random.choice(dates, num_records),
    'CustomerID': np.random.randint(1, 200, num_records),
    'ProductID': np.random.randint(1, 50, num_records),
    'ProductCategory': np.random.choice(['Electronics', 'Clothing', 'Home', 'Beauty', 'Sports'], num_records),
    'QuantitySold': np.random.randint(1, 10, num_records),
    'Price': np.round(np.random.uniform(5.0, 100.0, num_records), 2)
}

df = pd.DataFrame(data)
df['TotalSales'] = df['QuantitySold'] * df['Price']


'''Exploratory Data Analysis...'''

##We start by looking at the data structure and summary statistics...

# Preview the data
df.head()
# Summary statistics
df.describe()

# Basic visualizations
plt.figure(figsize=(12, 6))
sns.lineplot(data=df.resample('M', on='Date').sum()['TotalSales'])
plt.title('Monthly Sales Trend')
plt.xlabel('Month')
plt.ylabel('Total Sales')
plt.show()

plt.figure(figsize=(12, 6))
sns.barplot(x='ProductCategory', y='TotalSales', data=df.groupby('ProductCategory').sum().reset_index())
plt.title('Sales by Product Category')
plt.xlabel('Product Category')
plt.ylabel('Total Sales')
plt.show()

plt.figure(figsize=(12, 6))
top_products = df.groupby('ProductID').sum().sort_values(by='TotalSales', ascending=False).head(10).reset_index()
sns.barplot(x='ProductID', y='TotalSales', data=top_products)
plt.title('Top Selling Products')
plt.xlabel('Product ID')
plt.ylabel('Total Sales')
plt.show()










