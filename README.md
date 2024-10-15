### Developed by: NIVETHA A
### REG no:212222230101
### Date:

# Ex.No: 07                                       AUTO REGRESSIVE MODEL



### AIM:
To Implementat an Auto Regressive Model world population dataset.
### ALGORITHM:
1. Import necessary libraries
2. Read the CSV file into a DataFrame
3. Perform Augmented Dickey-Fuller test
4. Split the data into training and testing sets.Fit an AutoRegressive (AR) model with 13 lags
5. Plot Partial Autocorrelation Function (PACF) and Autocorrelation Function (ACF)
6. Make predictions using the AR model.Compare the predictions with the test data
7. Calculate Mean Squared Error (MSE).Plot the test data and predictions.
### PROGRAM
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.ar_model import AutoReg
from sklearn.metrics import mean_squared_error
import numpy as np
data = pd.read_csv('world_population.csv')
print(data.head())
data = data.sort_values('Year')
data.set_index('Year', inplace=True)
plt.figure(figsize=(10, 6))
plt.plot(data.index, data['Population'], marker='o')
plt.title('World Population Over Time')
plt.xlabel('Year')
plt.ylabel('Population')
plt.show()
train_size = int(len(data) * 0.8)  # Use 80% for training
train, test = data.iloc[:train_size], data.iloc[train_size:]
print(f'Train size: {len(train)}, Test size: {len(test)}')
plt.figure(figsize=(10, 6))
plt.plot(data.index, data['Population'], label='Historical Population', marker='o')
plt.plot(future_index, future_predictions, color='green', linestyle='--', label='Future Predictions')
plt.title('Future Population Predictions')
plt.xlabel('Year')
plt.ylabel('Population')
plt.legend()
plt.show()
print(future_predictions)
```

### OUTPUT:
PACF - ACF :

![376695807-bd936716-fd59-4777-840b-33ceadeeb47c](https://github.com/user-attachments/assets/c09d0c30-5062-4390-8380-262602ade3bb)

PREDICTION :

![376696073-0a697101-9652-4c68-b2fc-6aeb3d607778](https://github.com/user-attachments/assets/b18fe305-19c9-478a-9846-86edcc4fa4d7)


### RESULT:
Thus we have successfully implemented the auto regression function using python.
