# Intermediate-Assessment---Codeathon
1.Project Title: Logistics & Transportation- Fleet Performance & Delivery Efficiency
2.Problem Statement:
 A logistics company wants to analyze its fleet performance in terms of on-time deliveries, fuel efficiency, and cost per mile.
3.Dataset Description:

The project uses the following datasets:
Trip Table: Contains trip details such as Trip ID, Vehicle ID, Driver ID, Origin, Destination, Distance, Fuel Consumed, Delivery Status and Delivery Date.
Vehicle Table: Contains vehicle details such as Vehicle ID, Vehicle Type, Capacity and Maintenance Cost.
4.Data Cleaning and Transformation Using Excel Power Query
Data cleaning and transformation were performed using Power Query Editor in Microsoft Excel before importing the cleaned dataset into Power BI.

The following steps were performed:
Imported the logistics dataset into Excel Power Query Editor.
Checked the Fuel Consumed column for missing values. No missing values were found.
Grouped the data by Vehicle Type and calculated the average fuel consumption.
The average fuel consumption values were:
Mini-Truck: 105.71
Van: 84.66
Truck: 95.57
Identified the non-numeric value 116+666 in the Distance column and replaced it with Blank/Null.
Changed the Distance column data type to Whole Number
After completing the cleaning and transformation process in Excel Power Query, the cleaned data was used in Power BI for data modeling, DAX calculations and dashboard creation.
5.Data Modeling
The Trip Table and Vehicle Table were connected using the Vehicle_ID column.
A Many-to-One relationship was created between Trip_Table and Vehicle_Master, with Vehicle_Master on the One side.
6.DAX Measures
The following DAX measures were created:
1.1 Fuel Efficiency =
DIVIDE(SUM('Trip_Table_Duplicate'[Distance_km]),
    SUM('Trip_Table_Duplicate'[Fuel_Consumed_L]))
1.2.On_Time_Delivery % =
DIVIDE(
    CALCULATE(
        COUNTROWS('Trip_Table_Duplicate'),
        'Trip_Table_Duplicate'[Delivery_Status] = "On-Time"
    ),
    COUNTROWS('Trip_Table_Duplicate'),)
1.3 . Cost per km =
DIVIDE(
    SUM(Trip_Table_Duplicate[Fuel_Consumed_L]) * 95
    + SUM(Vehicle_Master[Maintenance_Cost]),
    SUM(Trip_Table_Duplicate[Distance_km]))
7. Dashboard Visualizations
- On-Time Delivery by Route: A bar chart showing on-time delivery percentage by Origin and Destination.
- Fuel Efficiency Trend by Month: A line chart showing fuel efficiency over time using Delivery Date.
- Cost per km: A KPI/Card visual displaying the cost per kilometer.
- On-Time Delivery Percentage: A Card visual displaying the on-time delivery percentage.
- Delivery Performance by Route: A map visual using Origin as Location, Destination in Tooltips and On-Time Delivery Percentage in Size.
8. Slicers
- Vehicle Type
- Delivery Status
- Delivery Date

9. Conclusion
The Power BI dashboard presents fleet performance and delivery efficiency through DAX measures, KPI cards, charts and a map visual.

    
    
  

