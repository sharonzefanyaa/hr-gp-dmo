# hr-gp-dmo

## **A. Answer questions using Spark SQL.**
1. Find the top 15 most common first names of the company's male’s employees. Create a report showing the first name, its frequency, and its rank.
### DATA DESCRIPTION:
Employee records are stored in the metastore table hr_records in the database hr_db.
### OUTPUT REQUIREMENTS:
• Place the result data in the hdfs directory: /user/studentID/solution
• Use a text format with a hyphen as the columnar delimiter.
• Order results by rank in ascending order.
• No ranks should be skipped if there are ranks with multiple names.
### SAMPLE RESULTS: 
Fidel:253:1 |
|Ralph:252:2 |
|Otis:250:3 |
|Terrance:250:3|
**Note: Total records of final output should be 1219**

2. 
### INSTRUCTIONS:
Use the EMR data to find the total number of emergency department visits that were due to influenza-like illness and/or pneumonia that resulted in hospitalization for the months of May, June & July.
### DATA DESCRIPTION:
Emergency department visits records are stored as Parquet files, compressed using gzip, and stored in the HDFS directory. You may access the directory using this path: /user/verulam_blue/data/emr_data
• The 'date_of_visit' column represents the date of hospital visit.
• The 'column li_pne_admissions' represent the count of influenza-like illness and/or pneumonia visits that went on to be admitted to the hospital. 
### OUTPUT REQUIREMENTS:
• Place the result data in the hdfs directory: /user/studentID/solution
• Results should show month of visit and number of hospitalizations.
• Use a text format with a tab as the columnar delimiter.
### RESULTS:
+---+----------+
|5 |200801|
|6 |113289|
|7 |122021|
+---+----------+

3. Working with the "gp_db" database use the "items" column from the metastore table "gp_rx" together with the "gp_address" table to find the total number of prescriptions made by each GP practice in the city of Bolton.
• The "items" column, in the metastore table "gp_rx", represents the "total number of items prescribed".
• The first 4 letters of postcodes for GP practices in Bolton are: 'BL1 ','BL2 ','BL3 '
### OUTPUT REQUIREMENTS
• Results data should be saved as a JSON file
• Place the result data in the hdfs directory: /user/studentID/solution
• Order results by "practice_code" in descending order.
### DATA DESCRIPTION
Schema for gp_address table:
+--------------------+----------------+
|col_name | data_type |
+--------------------+----------------+
|date | string|
|practice_code | string|
|surgery_name | string|
|address_1 | string|
|address_2 | string|
|address_3 | string|
|address_4 | string|
|postcode | string|
+--------------------+----------------+
Schema for gp_rx table:
+--------------------+-----------------+
|col_name | data_type |
+--------------------+-----------------+
|sha | string| 
|pct | string|
|practice_code | string|
|bnf_code | string|
|bnf_name | string|
|items | string|
|nic | string|
|act_cost | string|
|quantity | string|
|period | string|
+-----------------+-----------------+
### SAMPLE RESULTS
The first 2 lines of the results table should look as the table below:
+-------------------+--------------------------+------------------------+
|practice_code|surgery_name |nbr_prescriptions|
+---------------+-------------------------------+------------------------+
|Y04600 |BARDOC GP OOH | 3042|
| Y03641 |BOLTON COMMUNITY ...| 2267|
