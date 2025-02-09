# Trans-Border Freight Data Analysis
Trans-Border Freight Data Analysis using the CRISP-DM methodology

---
### Introduction:
Trans-border freight (the movement of goods across international boundaries) is a cornerstone of the global economy. It facilitates trade, fosters economic growth, and promotes cultural exchange. In the United States, the Bureau of Transportation Statistics (BTS) provides comprehensive data that underscores the significance of trans-border freight, particularly with neighbouring countries Canada and Mexico.

According to BTS, in 2023, the United States earned $773.9 billion worth of total freight flows with Canada and $798.8 billion with Mexico, encompassing all modes of transportation. Trucking dominated these exchanges, accounting for 56% ($435.7 billion) of US - Canada trade and 70.2% ($560.6 billion) of US - Mexico trade. Rail transport also played a significant role, with $113.9 billion in trade with Canada and $95.4 billion with Mexico.

While trans-border freight is economically beneficial, it also poses environmental challenges. The transportation sector is a significant contributor to greenhouse gas (GHG) emissions. According to the BTS, in 2013, transportation was responsible for about 27% of all GHG emissions in the United States, with medium and heavy-duty trucks accounting for a substantial portion.

The benefits of trans-border freight are undeniable, but, it is important to prioritize safety and sustainability to address environmental concerns and ensure the well-being of communities.

### Problem Statement:
This Trans-Border Freight Data Analysis project aims to enhance the efficiency, sustainability, and safety of freight across North American borders. Given the increasing volume of goods transported across various modes (vessel, rail, air, truck, etc), there is a need to identify inefficiencies, reduce environmental impact, and ensure optimal economic performance. The key objective here is to identify inefficiencies, recognize patterns, and propose actionable solutions to improve overall performance and sustainability while minimizing delays, costs, and environmental hazards.

### Analytical Questions
- What are the top commodities transported between the US, Canada, and Mexico by value and weight?
- Which US states have the highest volume of trade with Canada and Mexico?
- What are the most frequently used modes of transportation for trans-border freight?
- How do freight costs vary by transportation mode and commodity type?
- How has the volume of trans-border freight changed over the years?
- Are there seasonal variations in freight movement across different transportation modes?
- What is the distribution of containerized versus non-containerized freight?
- Which departure points (DEPE) handle the most significant freight volume?
- What are the most common trade routes for each transportation mode?
- How do economic disruptions (e.g., trade policies, global events) impact freight movement?
- What is the environmental impact of different transportation modes based on fuel consumption or emission estimates?
- How do transportation inefficiencies (e.g., congestion points, underutilized infrastructure) affect freight costs and delivery times?

### Overview of the Datasets
The datasets contain trans-border freight transportation data, capturing various aspects of goods movement between the US, Canada, and Mexico. The data is structured into three datasets:

- dot1: Includes information on trade type, US states, departure points, mode of transportation, state/province in Mexico and Canada, country, value, shipping weight, freight charges, domestic/foreign classification, and containerization.
- dot2: Similar to dot1 but includes a COMMODITY2 column in place of DEPE to specify the type of goods transported.
- dot3: Focuses on departure points, commodity classification, transportation modes, country, and freight details, omitting US state details.

These datasets provide insights into freight movement, trade patterns, transportation modes, costs, and geographic distributions of cross-border goods.
