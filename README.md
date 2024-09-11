### NAME  : KARTHIKEYAN R
### Reg.No:212222240046
### Date  :
# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

# Load the weather dataset
weather_data = pd.read_csv("/path/to/weather_data.csv")

# Print the columns of the DataFrame to check their exact names
print(weather_data.columns)

# Extract the 'PRCP' column (precipitation data) for ACF calculation
prcp_data = weather_data['PRCP'].values

# Calculate mean and variance
mean_prcp = np.mean(prcp_data)
var_prcp = np.var(prcp_data)
```
```
# Normalize the data (subtract mean and divide by standard deviation)
normalized_prcp = (prcp_data - mean_prcp) / np.sqrt(var_prcp)

# Compute the ACF for the first 35 lags
lags = range(35)
acf_values = [np.corrcoef(normalized_prcp[:-lag], normalized_prcp[lag:])[0, 1] if lag != 0 else 1 for lag in lags]

# Plot the ACF results
plt.figure(figsize=(10, 6))
plt.stem(lags, acf_values, use_line_collection=True)
plt.title('Autocorrelation Function (ACF) for Precipitation Data')
plt.xlabel('Lag')
plt.ylabel('ACF')
plt.grid(True)
plt.show()

```
### OUTPUT:
![image](https://github.com/user-attachments/assets/d86e3c07-671a-4c60-ba86-a6968c4c1358)


### RESULT:
        Thus, the python code for implementing the auto correlation function is executed successfully.
