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
