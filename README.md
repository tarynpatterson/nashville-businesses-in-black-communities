# Businesses in Predominantly Black Communities in Nashville
*Capstone Project for Part-time Data Analytics Cohort #5 program at Nashville Software School.* 

### **Contents**  
- [Motivation and Questions](#Motivation)
- [Data Sources and Tools](#Data-Sources-and-Tools)
- [Data Analysis](#Data-Analysis)
- [Challenges](#Challenges)
- [Conclusions](#Conclusions)
 

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
*Back to [Contents](#Contents)*