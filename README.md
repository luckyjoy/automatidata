# Automatidata project
EDA and Visualization for NYC Taxi and Limousine Commission (TLC) Data
### **Project: EDA and Visualization for NYC Taxi and Limousine Commission (TLC) Data**

#### **Objective:**
Perform EDA on the NYC TLC dataset, clean the data, create visualizations with Python, and build an accessible Tableau dashboard to show taxi ridership patterns.

#### **Deliverables:**
1. **Python Notebook**:
   - **Data Cleaning & Structuring**: Prepare the dataset by handling missing values and formatting datetime columns.
   - **Visualizations**:
     - Box plot of ride durations.
     - Time series plot (by month or quarter) showing ride counts and trends.

2. **Tableau Dashboard**:
   - Map of NYC showing taxi trips by month.
   - Make it accessible with high-contrast colors and tooltips for users with visual impairments.

#### **Steps:**

1. **Python Notebook**:
   - **Clean Data**: Handle missing values, convert columns to datetime.
   - **Box Plot**: Show distribution of ride durations.
   - **Time Series Plot**: Show ride counts or average duration by month.

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
df = pd.read_csv("nyc_tlc_data.csv")
df['pickup_datetime'] = pd.to_datetime(df['pickup_datetime'])
df['ride_duration'] = (df['dropoff_datetime'] - df['pickup_datetime']).dt.total_seconds() / 60

# Box plot
sns.boxplot(x=df['ride_duration'])
plt.show()

# Time series plot
df['pickup_month'] = df['pickup_datetime'].dt.to_period('M')
df.groupby('pickup_month').size().plot(kind='line')
plt.show()
```

2. **Tableau Dashboard**:
   - Map taxi trips by month using high-contrast colors for accessibility.
   - Add tooltips and clear labels for easy interpretation.

#### **Summary:**
Clean and visualize the NYC TLC data with Python (box plot and time series), then create a Tableau dashboard to show taxi trips by month, ensuring it's accessible for users with visual impairments.
