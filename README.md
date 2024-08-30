### Developed By: SHARAN MJ
### Register No: 212222240097
### Date:

# Ex.No: 01A PLOT A TIME SERIES DATA


## AIM:
To analyze and visualize the sales trends of a furniture store over time by creating a time series plot.

## ALGORITHM:

1.Load the Data: Import the sales dataset from a CSV file with appropriate encoding.
2.Data Preprocessing: Convert the order date to datetime format and filter for furniture sales.
3.Group and Aggregate Data: Group sales by order date and aggregate the total sales for each date.
4.Plot the Time Series: Create a time series plot of the aggregated sales data using matplotlib.
5.Interpret the Plot: Analyze the plot to identify trends, seasonality, and anomalies in the sales data.
<br />
<br />


## PROGRAM:


```python

import pandas as pd
import matplotlib.pyplot as plt


data = pd.read_csv('/content/Super_Store_data.csv',encoding='ISO-8859-1')  


data['Order Date'] = pd.to_datetime(data['Order Date'])

furniture_data = data[data['Category'] == 'Furniture']

furniture_sales = furniture_data.groupby('Order Date')['Sales'].sum().reset_index()

# Plot the time series
plt.figure(figsize=(14, 7))
plt.plot(furniture_sales['Order Date'], furniture_sales['Sales'], marker='o', color='b')
plt.title('Furniture Sales Over Time')
plt.xlabel('Date')
plt.ylabel('Sales')
plt.grid(True)
plt.show()
```
<br />
<br />
<br />
<br />

## OUTPUT:
![Screenshot 2024-08-23 215425](https://github.com/user-attachments/assets/4d158fc6-1c6d-4d44-a064-29a0eababb82)


# RESULT:
Thus we have created the python code for plotting the time series of given data.
