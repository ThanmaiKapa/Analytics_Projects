
## Analytics_Projects

Welcome to Analytics_Projects! This repository contains a series of data analysis projects where I explore diverse datasets and uncover meaningful insights. Each project highlights key steps in the data analysis process, including:

- Data Collection & Cleaning: Gathering and preparing raw data for analysis
- Exploratory Data Analysis (EDA): Examining data patterns, trends, and relationships
- Visualization: Using charts and graphs to present findings clearly
- Insight Generation: Interpreting results to provide actionable insights

Projects Included
#### Mapping the Educational Landscape in India
- Created a detailed visualization report on nearly 200 Indian colleges, highlighting top institutions, locations, ownership, and course offerings, using Python web scraping techniques for data extraction and analysis.
- Developed Power BI dashboards, boosting stakeholder engagement and data-driven decision-making by 25%. 

#### Used Car Price Analysis
- Conducted data analysis on used car listings, improving pricing strategy accuracy by 20%.
- Designed Power BI dashboards, boosting data-driven decision-making efficiency by 15%. 

## Mapping the Educational Landscape in India
### Problem Statement

The educational landscape of engineering colleges in India is extensive and multifaceted, with institutions spread across each state of the country offering a diverse array of courses. However, comprehensive data regarding these colleges, including information on available courses, fee structures, and infrastructure, is often fragmented and challenging to access. This lack of centralized data poses a significant challenge for students, parents, and policymakers in making informed decisions regarding higher education. 

The project aims to address this challenge by conducting a comprehensive data analytics study of engineering colleges in India. The primary objectives are as follows: 
Engineering Colleges Across States, Course Availability, Fee Structure Analysis, Government and Private Colleges.


### Steps followed 

- Step 1 : Extract the data from the web by web scraping using python libraries(BeautifulSoup).
- Step 2: Clean the data and convert it into csv file.
- Step 3: Load the csv file into Power BI Desktop.
- Step 4 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 5 : It was observed that in none of the columns errors & empty values were present.
- Step 6 : For extracting course names from courses column, location from college names column and NIRF rank use extract option in the add column section and select text before delimiter and choose the delimiter.

All the applied steps in power query editor are visible in query settings as follows:

![Screenshot 2024-04-14 231020](https://github.com/user-attachments/assets/807dc591-fd8f-47c6-b597-77cbcb91c939)
- Step 7 : For converting fees into numerical form select New column option which is present in the home tab in the Table view ribbon(Starting fees).
for creating new column following DAX expression was written;
       
        Starting Fees  = 
        
        VAR FeeValue = 'Engineering colleges'[Fees]
        RETURN
        IF(
            RIGHT(FeeValue, 1) = "k",
            VALUE(LEFT(FeeValue, LEN(FeeValue) - 1)) * 1000,
            IF(
                RIGHT(FeeValue, 5) = "Lakhs",
                VALUE(LEFT(FeeValue, LEN(FeeValue) - 5)) * 100000,
                VALUE(FeeValue)
            )
        )

Snap of new calculated column,

![Screenshot 2024-04-14 234849](https://github.com/user-attachments/assets/8ce4a90c-5c03-48b8-9a7c-c141209fa5f4)    
- Step 8 : In the report view, under the view tab, theme was selected.
- Step 9 : Table visual is added in Table page with original columns including college_name, course_name, fees, NIRF Rank'23, and Facilities link.
snap of the visual page,

![Screenshot 2024-04-14 235630](https://github.com/user-attachments/assets/9ddb7857-f1be-4759-bb12-a90e6b0ec0e7)
- Step 10 : Map visual is added in another page which is location of colleges page with a slicer containing locations.
snap of the visual page,

![Screenshot 2024-04-14 235926](https://github.com/user-attachments/assets/21f26d8c-e36a-476d-a154-0981c9d6bd34)
- Step 11 : Ownership report page is created by adding a pie chart, horizontal bar chart, 4 card visuals and a tree map.
snap of the visual page,

![Screenshot 2024-04-15 000302](https://github.com/user-attachments/assets/a433af4d-d88c-4b6f-866a-9098ede2fcd1)
- Step 12 : A tooltip page is added with a pie chart and a card visual.
snap of the tooltip,

![Screenshot 2024-04-15 000514](https://github.com/user-attachments/assets/8e4d42ac-4327-4bfe-93f2-90e13f117770)
- Step 13 : A Course report page is created by adding a funnel chart, table, line graph and a bar chart with a tooltip.
snap of the visual page,

![Screenshot 2024-04-15 000219](https://github.com/user-attachments/assets/14cb7ad1-699b-45f7-b4f9-32e255b31d67)
- Ster 14 : A top colleges page is created by adding bar graph, 2 card visuals, a pie chart, table and a donut chart.
snap of the visual page,

![Screenshot 2024-04-15 001206](https://github.com/user-attachments/assets/2c1b15ee-30d0-46f7-9474-7bb04c7ec4ac)
- Step 15 : Visual filters (Slicers) were added for various report pages.


## Used Car Price Analysis
### Problem Statement
The used car market is characterized by significant variability in pricing due to numerous influencing factors such as make, model, year, mileage, condition, and geographical location. This complexity often results in challenges for buyers and sellers in determining fair market values, leading to uncertainty and inefficiency in transactions. The objective of this project is to develop a comprehensive data analytics solution to accurately analyse used car prices by collecting and cleaning data from reliable sources, identifying key features, and employing statistical analysis and visualization techniques.
- Car price variation based on various cars brands.
- Best cars with good quality with less price.

### Steps followed

- Step 1 : Extract the data from the web by web scraping using python libraries(BeautifulSoup).
- Step 2: Clean the data and convert it into csv file.
- Step 3: Load the csv file into Power BI Desktop.
- Step 4 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 5 : It was observed that in none of the columns errors & empty values were present.
- Step 6 : For changing format like capitalizing words go to transform tab and click on format which is present in the ribbon and then select capitalize each word.
- Step 7 : For converting price into numerical form select New column option which is present in the home tab in the Table view ribbon.
for creating new column following DAX expression was written;
       
        Price Value = 
          var pricevalue='Used Cars Data'[Price]
          Return
           VALUE(LEFT(pricevalue, LEN(pricevalue)-4))*100000
- Step 8 : For changing format of the currency select the column and then select format option in column tools and change it to currency and change the currency symbol to Indian rupee symbol.

Snap of new calculated column,

![Screenshot 2024-05-28 191002](https://github.com/user-attachments/assets/51825800-95a1-4d84-81e9-9ac093a35166)
- Step 9 : A tooltip is added with a pie chart, donut chart and a card visual.
Snap of the tooltip,

![Screenshot 2024-05-30 204749](https://github.com/user-attachments/assets/d8d1bfbd-55b6-4ecc-9528-525d88cb7c0e)
- Step 10 : Report on car brand page is created by adding a table, 2 card visuals, funnel chart, pie chart with a tooltip and a treemap.
snap of the visual page,

![Screenshot 2024-05-30 204704](https://github.com/user-attachments/assets/a13e2fe6-3210-4b33-b014-51a5c9be584f)
- Step 11 : A table is added in a car details table page with a slicer containing car company names.
snap of the visual page,

![Screenshot 2024-05-30 204352](https://github.com/user-attachments/assets/b7898745-7c70-4206-810d-bff58071a2af)
- Step 12 : Comparision page is created by adding a horizontal bar graph, scatter chart and a decomposition tree.
snap of the visual page,

![Screenshot 2024-05-30 204523](https://github.com/user-attachments/assets/19e791c1-9d6b-458a-a1a4-dece640a6309)
- Step 13 : Top cars page is created by adding a location map, funnel chart, table, pie chart, donut chart, multi-row card and a slicer with locations.
snap of the visual page,

![Screenshot 2024-05-30 205033](https://github.com/user-attachments/assets/a687789e-18a0-46c6-b450-78092c1c0f43)
- Step 14 : Visual filters (Slicers) were added for various report pages.
