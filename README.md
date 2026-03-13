**🏡 Real Estate Market Analysis Dashboard (Power BI)**
**📊 Project Overview**

This project presents an interactive Real Estate Dashboard built using Power BI to analyze property listings, market trends, and agent performance.
The dashboard provides insights into property status distribution, price trends, days on market, and property type analysis, helping users understand real estate market dynamics.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/dc95069b-ca32-4907-9267-def670ca95a5" />

**🎯 Project Objective**

The objective of this project is to analyze real estate property data and build an interactive dashboard that enables users to:

Monitor property status (Sold, Pending, For Sale)

Track price trends and market inventory

Analyze days on market performance

Identify property type distribution

Evaluate listing agent activity

**📈 Key Insights**
1️⃣ Property Status Distribution

Total Properties: 3000

Sold: 1045 (34.83%)

Pending: 998 (33.27%)

For Sale: 957 (31.90%)

This indicates a balanced and active housing market.

2️⃣ Days on Market Analysis

Properties listed between 31–90 days show higher transaction activity, suggesting that most sales occur within this time frame.

3️⃣ Price Trend Insights

The dashboard tracks total property values across different statuses, allowing users to compare:

Current market inventory value

Value of completed sales

4️⃣ Property Type Analysis

The dataset includes different property types such as:

Apartments

Condos

Townhouses

Single Family Homes

This helps analyze buyer preferences and property demand.

5️⃣ Agent Listing Analysis

The dashboard shows listings handled by agents from agencies like:

Compass

Century 21

Keller Williams

RE/MAX

This helps visualize agent distribution and potential performance insights.

🛠 Tools & Technologies

Power BI

DAX (Data Analysis Expressions)

Data Modeling

Data Visualization

**📂 Dataset Features**

The dataset contains the following columns:
Price
Address
City
Zipcode
State
Bedrooms
Bathrooms
Area (Sqft)
Lot Size
Year Built
Days on Market
Property Type
MLS ID
Listing Agent
Status

**📊 Key DAX Measures**

Total_Propertise = 
 COUNTROWS(RealEstate_Dataset)

Total_Sale_Price = 
CALCULATE(
    SUM(RealEstate_Dataset[Price]),
    'RealEstate_Dataset'[Status] = "For Sale"
)

Total_Sold_Price = 
CALCULATE(
    SUM(RealEstate_Dataset[Price]),
    'RealEstate_Dataset'[Status] = "Sold"
)

Total_Pending_Price = 
CALCULATE(
    SUM(RealEstate_Dataset[Price]),
    'RealEstate_Dataset'[Status] = "Pending"
)

Proprtise_ForSale = 
CALCULATE(
    COUNTROWS(RealEstate_Dataset),
    'RealEstate_Dataset'[Status] = "For Sale")

Propertise_Sold = 
 CALCULATE(
    COUNTROWS(RealEstate_Dataset),
    RealEstate_Dataset[Status] = "Sold")

Propertise_Pending = 
CALCULATE(
    COUNTROWS('RealEstate_Dataset'),
    'RealEstate_Dataset'[Status] = "Pending")

%_Propertise_ForSale = 
DIVIDE(
    [Proprtise_ForSale],
    [Total_Propertise],
    0
)

%_Propertise_Sold = 
DIVIDE(
    [Propertise_Sold],
    [Total_Propertise],
    0
)

%_Propertise_Pending = 
DIVIDE(
    [Propertise_Pending],
    [Total_Propertise],
    0
    )


