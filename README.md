## Car Prices and Sales Dashboard

I recently completed a Microsoft Power BI dashboard project using a Car Prices dataset sourced from Kaggle. This project highlights key metrics in car sales and pricing, with insights into dealership distribution, sales performance, revenue, and customer preferences. Here’s an overview of the steps taken in this analysis.

### Research Questions

I began by opening the dataset in Microsoft Excel to get an initial overview. From this, I identified the following research questions:

•	Total number of auto dealerships
•	Total units sold
•	Total revenue generated
•	Percentage of vehicles with automatic vs. manual transmission
•	Most popular car models
•	Most expensive car models
•	How vehicle condition affects overall sales
•	Number of auto dealerships per state
•	Most preferred vehicle colors among buyers
•	States with the highest car sales and revenue from vehicle sales
•	Car condition most associated with high sales
•	Yearly overall sales performance

### Data Cleaning and Loading

During data cleaning, I noticed that the 'saledate' column was formatted in a way incompatible with Power BI. To resolve this, I used Python’s Pandas library to convert it to a compatible format, as shown in the code snippet below.
````
import pandas as pd

file = pd.read_csv("C:/Users/HP/Documents/car_prices.csv")
file.head()
file.info()
file['saledate'].head()
file['saledate'] = file['saledate'].str.replace(r"\s\(.+\)", "", regex=True)
file['saledate'] = pd.to_datetime(file['saledate'], errors='coerce',utc='True')
file['saledate'] = pd.to_datetime(file['saledate'], format="%a %b %d %Y %H:%M:%S %p %Z", errors='coerce')
file['saledate'].dtype
file['saledate'].head()
file.to_csv("C:/Users/HP/Documents/modified_car_prices.csv", index=False)

````

### Visualization

The dashboard includes a variety of visuals—horizontal and vertical bar charts, maps, donut charts, and tables—to present the data clearly and effectively.
![Screenshot 2024-11-06 202220](https://github.com/user-attachments/assets/39933682-4925-4e3c-a4c9-663084d6d5df)

![Screenshot 2024-11-06 202320](https://github.com/user-attachments/assets/7d4d320c-5af7-4bd2-b567-a306a7661902)


### Observations and Findings

•	Transmission Preference: Cars with automatic transmissions are far more popular than those with manual transmissions.
•	Top Car Brand: Ford is the most sought-after brand among customers.
•	Body Type: Sedans are the most preferred body type in the U.S.
•	Vehicle Condition: Cars in good, excellent, and average conditions have significantly higher sales than those in poor condition, likely due to reliability concerns.
•	Revenue by State: Florida generates the highest revenue from car sales, followed closely by California and Pennsylvania.
•	Dealership Distribution: California has the most auto dealerships, with Florida and Pennsylvania following closely.
•	Color Preference: Black is the most preferred exterior color, with white as a close second.
•	Most Expensive Car: The Ferrari 458 Italia is the most expensive car sold in the dataset.
•	Mileage and Profit: Low-mileage cars generated the highest profits over time.


