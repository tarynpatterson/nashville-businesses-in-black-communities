# Businesses in Predominantly Black Communities in Nashville
*Capstone Project for Part-time Data Analytics Cohort #5 program at Nashville Software School.* 

### **Contents**  
- [Motivation and Questions](#Motivation)
- [Data Sources and Tools](#Data-Sources-and-Tools)
- [Data Analysis](#Data-Analysis)
- [Challenges](#Challenges)
- [Conclusions](#Conclusions)
- [Use Case Scenario #1](#Use-Case-Scenario-#1)
- [Use Case Scenario #2](#Use-Case-Scenario-#2)
 

### **Motivation and Questions**   
I originally started this project wanting to shed a light on black-owned businesses and the types of businesses in predominantly black communities. As I dug deeper into the data, I found out black-owned businesses make up only 7.9% of all businesses in Davidson County (https://overheardonconferencecalls.com/business/best-cities-for-black-owned-businesses/). I also came across a lot of literature about what’s being called “The Great Resignation” – people quitting their jobs and either entering new jobs/fields or going into business for themselves. I found that 4.3 million business applications were filed in 2020, which is the most that have been filed in a decade and a half. In Davidson County alone, 12,753 applications were filed, up about 18.5% from 2019. So, I thought, instead of focusing on only Black-Owned businesses in Black communities, I’d analyze data on the types of businesses in these communities and use that to create a dashboard for community members to see what types of businesses are in their communities.   

*Back to [Contents](#Contents)*

### **Data Sources and Tools**   
**Data Sources**   
Census Data: Census Reporter. This website pulls census data from the 2019 5-year American Community Survey

Business Data: Google Places API (code heavily adopted from Nashville Food Deserts).

**Tools**
Python/Jupyter Notebooks for gathering and analysis of data

Tableau for data visualization     

*Back to [Contents](#Contents)*

### **Data Analysis**
Created a Percentage of Total Population column in the census data geojson file and filtered the dataframe to only include census tracts in Davidson County with a Black population of 50% or more. 
Obtained the length of the perimeter and centroid of each tract’s polygon and used that to get an approximate radius. I added a half mile buffer to this radius to make sure nothing got left out. 
Used the centroid and radius for each tract and ran these through the Google Places API to get businesses information on a set different business types, created a dataframe with the info and got rid of any duplicates. 
Performed a spatial join between the Census dataframe and the businesses dataframe to get only businesses within the tracks with a predominantly black population.

*Back to [Contents](#Contents)*

### **Challenges**
The main challenge I faced was categorizing the business types. The Google API will return at most 60 results per run, and you can only search for 1 business category at a time. As such, this is not an exhaustive list of all businesses in these Census tracts. 

Google also will give multiple business types to one business, and many were listed simply as “point of interest”, so I had to be mindful of that when cleaning and categorizing my data. 

*Back to [Contents](#Contents)*

### **Conclusions**
[Nashville Businesses in Black Communities - Tableau Dashboard](https://prod-useast-b.online.tableau.com/#/site/tarynpatterson/views/NashvilleBusinessesinBlackCommunities/NashvilleBusinessesinBlackCommunities?:iid=3)

![Nashville Businesses in Black Communities - Tableau Dashboard](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/NBBC_Dashboard.PNG)

*Back to [Contents](#Contents)*

### **Use Case Scenario #1** 
An auto-machanic has been primarily working out of her home garage, but is looking to expand to add a Black-owned brick and mortar location in her community. She lives in the South Antioch, Tennessee area, near census tract 156.30. She uses the dashboard "type" drop-down menu to first get an idea of where auto services are located in predominantly Black communities.
![Auto Services Search](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/auto%20services.PNG)

She then narrows down to her own community. She finds there are 3 auto services businesses in the area. She can now do some market research on these companies to gain some insights on the operation of her own business. 
![Auto Services Search 156.30](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/auto%20services%20156.30.PNG)

She knows she is going to need certain equipment for operation, and also hardware. Since she's wanting to invest in her own community, she keeps the search on census tract 156.30 and changes the search type to "equipment/supplies" and "hardware store". She notices there are multiple equipment and supplies companies in her area, but no hardware stores. She then expands her search to include all predominantly Black communities and narrows the search to "hardware" only. 
Now she has compiled a list of equipment and hardware companies and can begin research on which will best suit her needs for her new business.
![Equipment and Services and Hardware Search](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/equipment%20and%20supplies%20and%20hardware%20156.30.PNG) ![Hardware Search](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/hardware%20stores.PNG)

*Back to [Contents](#Contents)* 

### **Use Case Scenario #2**
A man who lives in the Whites Creek Area (census tract 101.05) is traveling to downtown Nashville every day for work. He's wanting to change jobs to something closer to home. He uses the dashboard to see what types of businesses are in his community. 
![Businesses 101.05 Search](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/101.05.PNG)

He notices that there are not many job options in his immediate area, so he expands his search to include two of the surrounding census tracts, tracts 101.06 and 109.03. He's able to see that the most prominant types of businesses in this area are medical services, restaurants, and grocery stores. Since he has prior experience in the medical field, he narrows his search to include only medical service companies in this area. He now has an the name and location of different medical companies close to home to start his job search. 
![Whites Creak area Search](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/whites%20creak%20job%20search.PNG) ![Medical Services Search](https://github.com/tarynpatterson/nashville-businesses-in-black-communities/blob/main/images/medical%20services.PNG)

*Back to [Contents](#Contents)*