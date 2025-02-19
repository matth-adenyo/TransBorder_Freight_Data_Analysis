# Trans-Border Freight Data Analysis
Trans-Border Freight Data Analysis using the CRISP-DM methodology

------------------------------------------------------------

## Introduction
Trans-border freight (the movement of goods across international boundaries) is a cornerstone of the global economy. It facilitates trade, fosters economic growth, and promotes cultural exchange. In the United States, the Bureau of Transportation Statistics (BTS) provides comprehensive data that underscores the significance of trans-border freight, particularly with neighbouring countries Canada and Mexico.

According to BTS, in 2023, the United States earned $773.9 billion worth of total freight flows with Canada and $798.8 billion with Mexico, encompassing all modes of transportation. Trucking dominated these exchanges, accounting for 56% ($435.7 billion) of US - Canada trade and 70.2% ($560.6 billion) of US - Mexico trade. Rail transport also played a significant role, with $113.9 billion in trade with Canada and $95.4 billion with Mexico.

While trans-border freight is economically beneficial, it also poses environmental challenges. The transportation sector is a significant contributor to greenhouse gas (GHG) emissions. According to the BTS, in 2013, transportation was responsible for about 27% of all GHG emissions in the United States, with medium and heavy-duty trucks accounting for a substantial portion.

The benefits of trans-border freight are undeniable, but, it is important to prioritize safety and sustainability to address environmental concerns and ensure the well-being of communities.

## Problem Statement
This Trans-Border Freight Data Analysis project aims to enhance the efficiency, sustainability, and safety of freight across North American borders. Given the increasing volume of goods transported across various modes (vessel, rail, air, truck, etc), there is a need to identify inefficiencies, reduce environmental impact, and ensure optimal economic performance. The key objective here is to identify inefficiencies, recognize patterns, and propose actionable solutions to improve overall performance and sustainability while minimizing delays, costs, and environmental hazards.

### Analytical Questions
- Which US states have the highest value of trade with Canada and Mexico?
- Which US port or district has the highest value of trade with Canada and Mexico?
- What is the contribution of trade value by country?
- Is there any difference in the distribution of trade value by Export and Import?
- What is the total trade value by mode of transportation?
- What are the top commodities transported across the U.S.-Canada and U.S.-Mexico borders, and how do they vary by mode of transportation?
- What are the most frequently used modes of transportation for trans-border freight?
- How has the volume of trans-border freight changed over the years?
- What are the primary trends in freight movement across different transportation modes over the past five years?
- How do economic disruptions (e.g., trade policies, global events) impact freight movement?
- Which transportation mode has the highest inefficiencies in terms of cost, time, and environmental impact?
- Which ports or districts experience the highest congestion or delays?
- Which transportation modes have the highest carbon footprint based on freight weight and distance?
- Are there underutilised transportation modes or routes that could be optimised?
- What data-driven recommendations can be provided to improve cross-border freight transportation?

## Overview of the Datasets
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

## Data Inspection/Exploration
The *dot1_MMYY, dot2_MMYY*, and *dot3_MMYY* are present in all the months for all the years. The *dot1_ytd_MMYY, dot2_ytd_MMYY*, and *dot3_ytd_MMYY* (where **MM** is the month, e.g January represented as **01** and **YY** is the last two digits of the year, e.g 2020 represented as **20**) are not present in some of the folders such as all months in 2024 and some months in 2023. In addition, March 2024 has only two datasets, *dot1_0324 and dot2_0324*. The dataset with **ytd** is cumulative. For example, **dot1_ytd_0420** in the April 2020 folder contains dataset from January 2020 to data. This means that to use the **ytd** data for analysis, one must use the one in the last month of that year since it is a cumulative dataset from the first month of that year to the last month of that same year.

Furthermore, December 2022 contain additional datasets named *dot1_2022, dot2_2022*, and *dot3_2022* which don't have the month column. 

In this project, dot1, dot2, and dot3 underscore the month and the year (that is **dot1_MMYY, dot2_MMYY, dot3_MMYY**) are used since they are the datasets that are consistent in all months of all years. All other datasets that don't follow this naming pattern are left out.

**Excel** was then used to perform a preliminary inspection of some of the datasets where *filter* was applied to check for empty cells in important columns and data structure was also checked to see if each column contained the expected data type.

## Data Reading
This is a large dataset and when dealing with such datasets, loading everything into memory at once can put excessive pressure on system resources. This can lead to slow performance, memory errors, or even system crashes. To prevent this, the dataset is read in chunks rather than all at once.
- First, instead of reading the full dataset, only a small sample is read (1000 rows) from *dot1_0420*. This was used to estimate how much memory a single row occupies without consuming too much memory upfront.
- The total memory usage of the sample DataFrame was then computed and divided by 1000 to give the approximate memory consumption of a single row in bytes.
- **psutil** library was then used to get the total available system RAM and 10% of that was allocated as budget memory for reading datasets to prevent excessive memory consumption.
- The chunksize was then calculated by dividing the *budget memory* by the *approximate memory consumption of the single row* to get the number of rows that can fit within the allocated 10% memory budget.
- The chunksize was converted to *integer* to get a whole number.

After the above steps, next is to loop through all the folders to read the datasets. The folders in each year are named with the *first three letters of their month* and the datasets in them that I need for this project are named as **dot1-3_the month's number and last two digits of the year** (e.g. a data file in the folder *Jan 2020* inside the folder *2020* have the name *dot1_0120, dot2_0120,* and *dot3_0120*). To be able to read only these datasets from each folder, I mapped each month's name to its number (e.g. **Jan** as **01**, **Feb** as **02**), and extracted it together with the last two digits of the year.

Next, I used **For Loop** to iterate through the *year and months* folders to load only datasets that match the pattern **dot1-3** underscore the *extracted month's number and year number* with the help of **os** and **glob** library.

Each dataset type (dot1, dot2 and dot3) is read in chunks and appended to the appropriate dataset type dictionary. Next, all dot1 were concatenated together, same as dot2 and dot3.

While this was going on, the **tqdm** library was used to keep track of the progress.

After concatenating all datasets, the shape of each was:
- All dot1: (1500485, 14)
- All dot2: (4101624, 14)
- All dot3: (915116, 12)

## Data Preparation
To prepare the way for analysis, all the ***new datasets*** (all_dot1, all_dot2 and all_dot3) were merged to have one *final_data*. The shape of this was *(6517225, 15)*.

This *final_data* was then explored and **Data Mapping** was performed on columns such as **TRDTYPE, DISAGMOT, COUNTRY, DF, USASTATE, MEXSTATE, CANPROV, COMMODITY2,** and **CONTCODE**. 
- All states marked **'XX'** in the *MEXSTATE* column were mapped as **OT** (*Unknown*) since it does not have any matching state in the data dictionary.
- Similarly, all **'1'** in the *CONTCODE* column were mapped as **Unknown** as no match was found in the data dictionary.

### Null Values
Since all datasets have been merged, the number of *null* values has increased. This occurs because some datasets do not contain certain columns. For example:

- **all_dot1** (1,500,485 rows) does not have the **COMMODITY2** column.
- **all_dot2** (4,101,624 rows) does not include the **DEPE** column.
- **all_dot3** (915,116 rows) lacks the **USASTATE**, **MEXSTATE**, and **CANPROV** columns.

Also, whenever there is trade between the US - Mexican States, the  Canadian Province column will be *null* and vice versa.

These missing columns introduce null values in the merged dataset but were not dropped because they would not affect the analysis.

## Methods Used in the Analysis
Several methods and techniques were used in this analysis to extract insights from the dataset. Below is a list of them:
- Data Mapping
- Data Concatenation
- Data Aggregation and Grouping
- Data Sorting and Filtering
- Data Visualisation
- Congestion and Inefficiency Analysis
- Trend Analysis
- Seasonal Decomposition

## Data Visualisation & Insights
To answer the **analytical questions,** various visualisation plots such as bar plots, line charts, trend analysis, etc were used. Below are the insights from them:
- Top U.S. states with the highest trade value with Canada and Mexico
The overall U.S. state with the highest trade value was **Texas** with over **$2,815 billion** followed by **Michigan** and **California** with over **$1,251 billion** and **$1,151 billion** respectively.

![image](https://github.com/user-attachments/assets/828652a1-7cb7-4097-8b55-de1c19ae49b3)

Further digging indicates that **Texas** generate over **$2,258 billion,** **California** generate **$790 billion** and **Michigan** generate over **$652 billion,** all by trading with *Mexico* and the rest with *Canada.*

![image](https://github.com/user-attachments/assets/b4283f11-0205-41a6-8397-1a2de819f05e)

This highlight shows **Mexico** as the *leading trading partner* of the **U.S** with a little above **50%** while **Canada** has a little below **50%**.

![image](https://github.com/user-attachments/assets/dc217fe2-b5cf-4833-9e06-dbe304df9270)

- Export vs. Import
Import Contributes over **$10,000 billion** trade value while Export contributes over **$8,000 billion** trade value.

![image](https://github.com/user-attachments/assets/6b94c0fe-47c3-4445-b376-5ee4a4fbdeb4)

Below is the breakdown country-wise:

![image](https://github.com/user-attachments/assets/b20a7a90-33df-4845-9c4a-4ec90a49c436)

- Trade by Port
Ports in **Texas** dominate trades with **Laredo** leading with over **$2,449 billion** trade values followed by **Detroit** with **$1,246 billion**

![image](https://github.com/user-attachments/assets/c3a64039-8a7b-4e11-a989-cfae609a6de7)

- Trade by Mode of Transportation
Truck transportation dominates cross-border trade, accounting for over **60%** of the total trade value. Rail and vessel transportation follow, with smaller shares. Pipeline transportation, while significant for certain commodities, represents a smaller portion of overall trade value.

![image](https://github.com/user-attachments/assets/3c853fd6-d27a-4136-bb57-a63ddf099360)

- Trade by Commodity Type
The top commodities include vehicles, mineral fuels, nuclear reactors, and electrical and machinery equipment. These categories represent the backbone of U.S. cross-border trade, reflecting the strong industrial and manufacturing ties between the U.S., Canada, and Mexico.

![image](https://github.com/user-attachments/assets/a7571937-d489-4033-aa85-75d89a4e501c)

- U.S. - North American Freight Flows Over Time
There was a steady increase in trade value from 2020 to 2024, with some seasonal fluctuations. The COVID-19 pandemic in 2020 caused a temporary dip in trade, but recovery was swift, and trade value rebounded strongly in 2021 and beyond. Consequently, 2024 also experienced a dip in trade value probably due to trade policy which may be caused by the presidential election.

![image](https://github.com/user-attachments/assets/eeb571f1-8711-45c1-b8a3-bfe995ad6f50)

A breakdown by country is shown below:

![image](https://github.com/user-attachments/assets/2562f19e-8366-4f28-91a9-e3ba572072af)

- Inefficiencies in Freight Flow
The analysis reveals that shipments with zero reported weight (SHIPWT = 0) still incurred high freight charges. This suggests potential inefficiencies, such as misreported or missing shipment weight data, fixed-cost pricing models that do not account for shipment weight, excessive administrative, or other hidden costs. These were mostly between U.S. - Canada freight flow.

![image](https://github.com/user-attachments/assets/43bab74e-ce7b-4c0f-984f-841e0017f20d)

Further analysis reveals instances where truck transport incurred high freight charges despite no recorded shipment weight. This inefficiency may be due to the use of truck transport for low or zero-weight shipments, leading to wasteful spending or lack of load consolidation, causing trucks to run below capacity.

![image](https://github.com/user-attachments/assets/ffd445ce-e4a0-4112-9e12-d53a818ebd90)

Top 10 High-Cost Trade Routes (in Million USD) reveal significant cost variations across different transportation modes and trade routes. Pipeline transport between the U.S. and Canada accounts for the highest freight costs, likely due to infrastructure and maintenance expenses.

![image](https://github.com/user-attachments/assets/00e50bdb-77d7-4aab-a43d-60be66fffa3c)

- Congestion Analysis
Analysing the transport route reveals that **pipeline** transport between the U.S. and Canada has the highest shipment weight suggesting *congestion* followed by **vessel** for Mexico and Canada.
Overall, Vessel transport has the highest shipment weight.

![image](https://github.com/user-attachments/assets/f850572e-582c-4fa5-9560-1056cc77ca65)

By port-wise, ports in **Chicago** receive the highest freight flow through **pipelines.**

![image](https://github.com/user-attachments/assets/af4ba44a-2538-493c-9708-002cb86671e5)

- Under Utilizated Routes
Hawaii to Mexico is the Least Utilized Route having the lowest shipment weight while Alaska to Mexico is the 10th most underutilized route.

![image](https://github.com/user-attachments/assets/0da9bb87-b163-44c6-b211-e41ee9cd9d04)

- Seasonal Decomposition
To further understand freight flow, seasonal decomposition was performed. The result reveals that shipments follow a seasonal pattern and show a general increase but a dip in 2024. Significant residuals were also noticed in some places suggesting external factors affecting shipments beyond trend and seasonality.

![image](https://github.com/user-attachments/assets/b2cf6869-c075-4848-9d28-dd413f8e2d89)

## Environmental Impact
Trucks have the largest carbon footprint contribution due to fuel consumption. The analysis reveals Trucks as the dominating mode of transport, even the count of Trucks with zero shipments was over 2 million.

## Recommendations
The following are recommended:
- Investment should be made in rail infrastructure and underutilized routes to reduce congestion.
- Greener fuel alternatives and carbon reduction strategies should be encouraged.
- Rail transport should be optimized for cost-effective trade.
- AI-driven logistics should be implemented for better freight management.
- Trade policies should be harmonized to minimize delays and inefficiencies

## Conclusion
Addressing inefficiencies in trans-border freight is crucial for enhancing sustainability and economic performance. By leveraging data-driven strategies, trade flow can be optimized, environmental impact minimized, and cost-effectiveness improved. Additionally, continuous research and technological advancements are essential for ensuring long-term improvements in the efficiency and sustainability of freight operations.
