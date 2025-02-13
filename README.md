# Trans-Border Freight Data Analysis
Trans-Border Freight Data Analysis using the CRISP-DM methodology

------------------------------------------------------------
Project in Progress...
------------------------------------------------------------

---
### Introduction:
Trans-border freight (the movement of goods across international boundaries) is a cornerstone of the global economy. It facilitates trade, fosters economic growth, and promotes cultural exchange. In the United States, the Bureau of Transportation Statistics (BTS) provides comprehensive data that underscores the significance of trans-border freight, particularly with neighbouring countries Canada and Mexico.

According to BTS, in 2023, the United States earned $773.9 billion worth of total freight flows with Canada and $798.8 billion with Mexico, encompassing all modes of transportation. Trucking dominated these exchanges, accounting for 56% ($435.7 billion) of US - Canada trade and 70.2% ($560.6 billion) of US - Mexico trade. Rail transport also played a significant role, with $113.9 billion in trade with Canada and $95.4 billion with Mexico.

While trans-border freight is economically beneficial, it also poses environmental challenges. The transportation sector is a significant contributor to greenhouse gas (GHG) emissions. According to the BTS, in 2013, transportation was responsible for about 27% of all GHG emissions in the United States, with medium and heavy-duty trucks accounting for a substantial portion.

The benefits of trans-border freight are undeniable, but, it is important to prioritize safety and sustainability to address environmental concerns and ensure the well-being of communities.

### Problem Statement:
This Trans-Border Freight Data Analysis project aims to enhance the efficiency, sustainability, and safety of freight across North American borders. Given the increasing volume of goods transported across various modes (vessel, rail, air, truck, etc), there is a need to identify inefficiencies, reduce environmental impact, and ensure optimal economic performance. The key objective here is to identify inefficiencies, recognize patterns, and propose actionable solutions to improve overall performance and sustainability while minimizing delays, costs, and environmental hazards.

### Analytical Questions
- 1
- 2
- 3
- 4

### Overview of the Datasets
The [dataset](https://azubiafrica-my.sharepoint.com/personal/emmanuel_agyen_azubiafrica_org/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Femmanuel%5Fagyen%5Fazubiafrica%5Forg%2FDocuments%2FTMP%2Fdata%2Ezip&parent=%2Fpersonal%2Femmanuel%5Fagyen%5Fazubiafrica%5Forg%2FDocuments%2FTMP&ga=1) is trans-border freight transportation data from 2020 to 2024, capturing various aspects of goods movement such as type of trade (Export or Import), mode of transportation (Truck, Air, Vessel, etc), US States, Mexican States, Canadian Province, commodity, US port, among others between the US - Canada, and US - Mexico.
- **2020:** contains 9 sub-folders from January to September
- **2021:** contains 12 sub-folders from January to December
- **2022:** contains 12 sub-folders from January to December
- **2023:** contains 12 sub-folders from January to December
- **2024:** contains 9 sub-folders from January to September

Each of these sub-folders contains 3 to 6 different CSV dataset files. The CSV files are named **dot1_MMYY, dot2_MMYY,** and **dot3_MMYY** for all sub-folders. Some years have additional CSV data files named **dot1_ytd_MMYY, dot2_ytd_MMYY,** and **dot3_ytd_MMYY** while others have **dot1_YYYY, dot2_YYYY,** and **dot3_YYYY** in addition.
### Columns in Each *dot*
### 1. dot1
- TRDTYPE: Trade Type Code
- USASTATE: US State Code
- DEPE: Port/District Code
- DISAGMOT: Mode of Transportation
- MEXSTATE: Mexican State Code
- CANPROV: Canadian Province Code
- COUNTRY: Country Code
- VALUE: Value of Goods in USD
- SHIPWT: Shipping Weight in Kg
- FREIGHT_CHARGES: Freight Charges in USD
- DF: Domestic/Foreign Code
- CONTCODE: Container Code
- MONTH: Month
- YEAR: Year

### 2. dot2
- TRDTYPE: Trade Type Code
- USASTATE: US State Code
- COMMODITY2: Commodity Classification Code
- DISAGMOT: Mode of Transportation
- MEXSTATE: Mexican State Code
- CANPROV: Canadian Province Code
- COUNTRY: Country Code
- VALUE: Value of Goods in USD
- SHIPWT: Shipping Weight in Kg
- FREIGHT_CHARGES: Freight Charges in USD
- DF: Domestic/Foreign Code
- CONTCODE: Container Code
- MONTH: Month
- YEAR: Year

### 3. dot3
- TRDTYPE: Trade Type Code
- DEPE: Port/District Code
- COMMODITY2: Commodity Classification Code
- DISAGMOT: Mode of Transportation
- COUNTRY: Country Code
- VALUE: Value of Goods in USD
- SHIPWT: Shipping Weight in Kg
- FREIGHT_CHARGES: Freight Charges in USD
- DF: Domestic/Foreign Code
- CONTCODE: Container Code
- MONTH: Month
- YEAR: Year

These datasets provide insights into freight movement, trade patterns, transportation modes, costs, and geographic distributions of cross-border goods.

### Data Inspection/Exploration
