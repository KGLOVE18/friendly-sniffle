# IoT Data Integration: Greenhouse Scenario

For this project, I combined three different IoT datasets into one CSV file. The goal was to make it easier to compare soil conditions, environmental conditions, and water pump activity in a greenhouse.

## The 3 Data Sources and Information Collected

The `source-data` folder contains three data files collected by devices in this deployment:

- `csv - Date, time, sensor ID, bed ID, soil moisture, soil temperature, and battery level
- `json - Air temperature, humidity, wind speed, and sunlight intensity
- `xml - Date, time, watering zone, flow rate, pump status, and activation mode

Questions I Wanted to Investigate
1. How do environmental conditions and soil conditions influence the amount of water a pump should distribute to plants?
2. Why might soil moisture remain low even when the water pump is running?
3. How do changes in temperature, humidity, and sunlight intensity relate to soil moisture and water pump activity?

## How I Combined the Files
1. I opened the soil CSV data in Excel and selected my sample.
2. I fixed an extra word at the beginning of the XML file that prevented Excel from importing it.
3. I used Power Query to import the XML file and turn its nested measurements into columns.
4. I used XLOOKUP to match environmental measurements to the soil readings by time.
5. I imported the JSON pump records and used COUNTIFS and AVERAGEIFS to summarize pump activity during the previous two hours for each soil reading.
6. I saved the combined worksheet as a CSV file so it could be used by a dashboard.

## What I Learned
This project helped me understand how combining different data sources can provide a better understanding of how an entire system operates. I also learned how important it is to organize data correctly, match timestamps, and handle missing information when preparing data for analysis.
