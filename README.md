# Trans-Border Freight Data Analysis
Trans-Border Freight Data Analysis using the CRISP-DM methodology

------------------------------------------------------------
Project in Progress...
------------------------------------------------------------

---
## Introduction
Trans-border freight (the movement of goods across international boundaries) is a cornerstone of the global economy. It facilitates trade, fosters economic growth, and promotes cultural exchange. In the United States, the Bureau of Transportation Statistics (BTS) provides comprehensive data that underscores the significance of trans-border freight, particularly with neighbouring countries Canada and Mexico.

According to BTS, in 2023, the United States earned $773.9 billion worth of total freight flows with Canada and $798.8 billion with Mexico, encompassing all modes of transportation. Trucking dominated these exchanges, accounting for 56% ($435.7 billion) of US - Canada trade and 70.2% ($560.6 billion) of US - Mexico trade. Rail transport also played a significant role, with $113.9 billion in trade with Canada and $95.4 billion with Mexico.

While trans-border freight is economically beneficial, it also poses environmental challenges. The transportation sector is a significant contributor to greenhouse gas (GHG) emissions. According to the BTS, in 2013, transportation was responsible for about 27% of all GHG emissions in the United States, with medium and heavy-duty trucks accounting for a substantial portion.

The benefits of trans-border freight are undeniable, but, it is important to prioritize safety and sustainability to address environmental concerns and ensure the well-being of communities.

## Problem Statement
This Trans-Border Freight Data Analysis project aims to enhance the efficiency, sustainability, and safety of freight across North American borders. Given the increasing volume of goods transported across various modes (vessel, rail, air, truck, etc), there is a need to identify inefficiencies, reduce environmental impact, and ensure optimal economic performance. The key objective here is to identify inefficiencies, recognize patterns, and propose actionable solutions to improve overall performance and sustainability while minimizing delays, costs, and environmental hazards.

### Analytical Questions
- 1
- 2
- 3
- 4

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
