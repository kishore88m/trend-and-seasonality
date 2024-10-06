# trend-and-seasonality

# Time Series Decomposition: Trend and Seasonality

This repository contains a Python script that decomposes a time series (in this case, tourist numbers) into **trend** and **seasonality** components using a simple moving average technique. The script reads the time series from a CSV file, estimates the trend, and computes the seasonality before visualizing the results in three subplots.

## Requirements
- **Python 3.x**
- **Pandas** for data handling
- **Matplotlib** for plotting

You can install the necessary libraries using:
```bash
pip install pandas matplotlib
```

## Usage

1. Ensure you have a CSV file with a column of data representing the time series (e.g., `TouristNumber`).
2. Replace the column name in the script (`'TouristNumber'`) with the actual column name from your file.
3. Run the script to generate the trend and seasonality decomposition.

### Loading the Data
```python
data = pd.read_csv("/content/data.csv")
y = data['TouristNumber']
```
- This loads the CSV file and selects the `TouristNumber` column, which is the time series data.

### Estimating the Trend
The **trend** is computed using a moving average with a window size `d`, which is chosen based on the length of the data. 
```python
def estimate_trend(y, d):
    # ...
```
- The function calculates the average of values around each time point using a sliding window.
- The window is adjusted dynamically for edge cases (start or end of the series).

### Estimating the Seasonality
The **seasonality** is calculated by dividing the original data by the trend component.
```python
def estimate_seasonality(y, d, trend):
    # ...
```
- This isolates the recurring patterns in the data by removing the trend.

### Plotting the Results
The script generates three subplots: 
1. The original time series
2. The trend component
3. The seasonality component

```python
plt.figure(figsize=(10, 6))
# Plot original data, trend, and seasonality
plt.tight_layout()
plt.show()
