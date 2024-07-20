![Python](https://img.shields.io/badge/python-3670A0?style=plastic&logo=python&logoColor=ffdd54) ![MySQL](https://img.shields.io/badge/MySQL-%234479A1?style=plastic&logo=mysql&logoColor=white
) ![Pandas](https://img.shields.io/badge/Pandas-%23150458?style=plastic&logo=pandas&logoColor=white) ![AmazonS3](https://img.shields.io/badge/Amazon_S3-FF9333?style=plastic&logo=amazons3&logoColor=black) ![Redshift](https://img.shields.io/badge/Amazon_Redshift-%238C4FFF?style=plastic&logo=amazonredshift&logoColor=black) ![AWSGlue](https://img.shields.io/badge/AWS_Glue-B2FF33?style=plastic&logoColor=black) ![Spark](https://img.shields.io/badge/Apache_Spark-%23E25A1C?style=plastic&logo=apachespark&logoColor=black) ![Neo4j](https://img.shields.io/badge/Neo4j-%234581C3?style=plastic&logo=neo4j&logoColor=white)

# SkillShift: Dynamic Skill Demand Analysis 

<img align="right" src="https://github.com/rashmishreev/DBMS---DATA-225-Course-Project/blob/main/Images/blog.png"> [Checkout the blog on Medium](https://medium.com/@rashmishree.veeraiah/empowering-job-seekers-in-the-market-with-information-above-and-beyond-the-stated-job-description-d0f98c753a4f)

### Motivation
The job market is swiftly evolving with a focus on technology and sustainability. Job seekers now prioritize factors such as work culture and societal impact.
LinkedIn, Indeed, and Glassdoor offer unique strengths in providing valuable data. Government websites like ONET and the US Department of Labor contribute insights as well.
Despite existing information, there is a need for a novel tool to track changing skills demand and employee perceptions. The motivation for this
data-driven solution stems from personal needs as job seekers, aiming to provide quantitative insights for staying competitive in the evolving market.

### Objective
Our information system aims to quantify changing skill demand, addressing a gap in understanding market needs. Unlike previous work, our innovative solution provides specific insights into evolving skills, aiding individual growth. Recognizing the importance of the employment index, our system can assist policymakers in timely workforce interventions for a healthy economy.

### Significance to the real world
Top economic policy researchers and consulting firms like McKinsey and Deloitte highlight significant shifts in skill demand due to automation, technology changes, and events like COVID-19. However, major job portals such as LinkedIn, Indeed, or Glassdoor lack analytical solutions for understanding these shifts. Our innovative solution provides granular insights into specific skill and tool demand changes, along with tracking shifts in employee perceptions post-external shocks like COVID-19, including phenomena like great resignation and employee dissatisfaction with returning to the office.

### Project Workflow
**Workflow 1**

> Raw CSV data was processed and cleaned using Python's PySpark and Pandas. The processed data was stored in an Amazon S3 bucket on AWS, crawled to the Glue Data Catalog, and underwent ETL processes using Glue jobs. Finally, the data was loaded into Amazon Redshift for analysis through SQL queries in the Redshift Query Editor V2.

<img align="centre" width="700" height="400" src=https://github.com/rashmishreev/DBMS---DATA-225-Course-Project/blob/main/Images/ProjectFlowAws.drawio.png>

**Workflow 2**

> The Skill attribute and related features were stored in a separate CSV file to adhere to the First Normal Form. Using Python Pandas, essential attributes for the Neo4J data model were mapped to this file. After importing the updated CSV into Neo4J AuraDB, the data model was constructed. The Graph Database was connected to the GraphXR Platform for visual analytics using the Neo4J Data Model's API Connection String.

<img align="centre" width="700" height="400" src=https://github.com/rashmishreev/DBMS---DATA-225-Course-Project/blob/main/Images/ProjectFlow3.drawio.png>

**Workflow 3**

> Normalized and cleaned CSV data is imported into the MySQL server via MySQL Workbench. Connection to the MySQL server is established using the Python/MySQL connector from a Python application, facilitating data analysis through SQL queries in MySQL Workbench and Python code.

![Workflow3](https://github.com/rashmishreev/DBMS---DATA-225-Course-Project/blob/main/Images/ProjectFlow2.drawio.png)
> [!NOTE]
> Workflow 1 and 3 were employed to reproduce the viable analytical solutions provided by established job portals in the market. Meanwhile, Workflow 2 was utilized to create one of our visual solutions, monitoring skill demand in the current job market.

### Data Modelling

Our data warehouse employs a star schema with 9 static dimensions corresponding to each entity type and a single fact table containing quantitative measures and foreign keys from all dimension tables as its composite primary key.

![ERD](https://github.com/rashmishreev/DBMS---DATA-225-Course-Project/blob/main/Images/erd.png)

**Reverse-engineered data model**

![reverse_engineered](https://github.com/rashmishreev/DBMS---DATA-225-Course-Project/blob/main/Images/reverse_engineered.png)

**Neo4j Data Model**

> The Neo4j data model below illustrates 14 nodes connected by edges that denote their relationships. Both nodes and edges are characterized by properties like jobDate, monthyr, etc.

![Neo4j](https://github.com/rashmishreev/DBMS---DATA-225-Course-Project/blob/main/Images/Neo4J_Modelling.png)

### Analytics and Data-Driven Results
> [!NOTE]
> Analysis was conducted using Python with MySQL, and some utilized Amazon Redshift's query editor v2.
1. Number of job openings by job type, sorted by companies with over 50 postings.
![1](https://github.com/rashmishreev/Empowering-job-seekers-with-information-beyond-the-job-description/blob/main/Images/no_of_jobs_CMO.png)
> This query analyzes job postings for Computer and Mathematical occupations by employers in 2019, 2020, and 2021. Numerous employers have more than 50 job openings for various roles.
2. List of 'Data Analyst' job postings in each U.S. state, sorted from most to least.
![2](https://github.com/rashmishreev/Empowering-job-seekers-with-information-beyond-the-job-description/blob/main/Images/DA_by_location.png)
> The Data Analyst role has the most job postings in California (251 openings), followed by Texas (210 openings). Job opportunities are greater in states where many companies have their headquarters.
3. What are the top 10 skills needed for a Data Analyst?
![3](https://github.com/rashmishreev/Empowering-job-seekers-with-information-beyond-the-job-description/blob/main/Images/DA_skills.png)
> For a data analyst in the industry, the most crucial skills include data analysis, Microsoft Excel, SQL, and effective communication.
4. Pay range for a Software Development Engineer at Google in different locations.
![4](https://github.com/rashmishreev/Empowering-job-seekers-with-information-beyond-the-job-description/blob/main/Images/location_salary.png)
> Job seekers should consider pay differences by location when choosing a career. We use the query above to help them input their role and firm name, providing insights into average maximum and minimum salaries across locations.
5. The career path of a Clinical Researcher, includes average salary, education, and experience.
![5](https://github.com/rashmishreev/Empowering-job-seekers-with-information-beyond-the-job-description/blob/main/Images/career_trajectory.png)
> In the displayed result, we illustrate the career progression for individuals in Clinical Research, advising on how they can advance in their chosen field and specifying the maximum salary they can anticipate at each career stage.

### The Complete ETL Workflow Overview

This high-level overview outlines the steps involved in the Extract, Transform, Load (ETL) process.

1. **Load Raw Data:**
   - Use Python's PySpark module and pandas library.
   - Load the raw CSV dataset into PySpark's RDD structure in Python.
2. **Data Transformation and Feature Engineering:**
   - Perform data transformations, feature engineering, and filter rows (e.g., filter out Internship jobs).
   - Divide the dataset into multiple tables, creating 9 dimensions and 1 fact table.
   - Store each table in separate CSV files.
3. **AWS Integration:**
   - Preprocess CSV files and load them into an S3 bucket, serving as a data lake on AWS using the command line interface.
   - Use a crawler to catalog the data on AWS Glue.
4. **Amazon Redshift Setup:**
   - Create a cluster on Amazon Redshift and the corresponding database.
   - Establish and test the connection to Redshift on AWS Glue.
5. **ETL Processing:**
   - Employ ETL jobs on AWS Glue for data type transformations, extracting month-year, quarter-year, and year from the job_date field, and removing duplicates.
6. **Loading Data into Redshift:**
   - Load the transformed data into Redshift from Glue using the previously created Glue job.
7. **Data Warehousing:**
   - Load all the tables into the Amazon Redshift Data Warehouse.

> :face_exhaling: TLDR: This ETL workflow encompasses loading raw data with Python, transforming it into multiple tables, integrating with AWS S3 and Glue for preprocessing, setting up Amazon Redshift for data warehousing, and executing ETL processes to load and refine data, ultimately facilitating comprehensive analysis and reporting. 
