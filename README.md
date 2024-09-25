#Developed by : Pravin Raj A
# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 


### AIM:
To Illustrates how to perform time series analysis and decomposition on the  Bit-Coin price Prediction monitoring.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
NAME: Pravin Raj A
REG_NO:212222240079
```
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the dataset
file_path = '/content/BTC-USD(1).csv'
data = pd.read_csv(file_path)

# Convert 'Date' to datetime format and set it as the index
data['Date'] = pd.to_datetime(data['Date'])
data.set_index('Date', inplace=True)

# Print the available columns 
print(data.columns)

# Perform time series decomposition 
# ----> Replace 'YOUR_COLUMN_NAME' with the actual name of the column you want to analyze
series = data['Volume']
decomposition = seasonal_decompose(series, model='additive', period=30)  # Assuming monthly seasonality (30 days)

# Plot the decomposed components: observed, trend, seasonal, and residual
plt.figure(figsize=(12, 8))

plt.subplot(411)
plt.plot(decomposition.observed, label='Observed')
plt.legend(loc='upper left')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')

plt.tight_layout()
plt.show()
```


### OUTPUT:

![Screenshot 2024-09-25 085919](https://github.com/user-attachments/assets/3afe52d2-2266-4cbe-a9e9-1e72cb20c023)

### RESULT:
Thus the python code for the time series analysis and decomposition is created and executed successfully.
