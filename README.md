# Empowering job seekers in the market with information beyond the stated job description

### Motivation:
The labor market is rapidly changing due to technology and sustainability priorities. Job seekers now prioritize factors like work culture and societal impact. Popular job sites, LinkedIn, Indeed, and Glassdoor, provide valuable data with unique strengths. Government websites like ONET and the US Department of Labor contribute insights. Despite existing information, there's a need for a novel tool to track evolving skills demand and employee perceptions. The motivation for this data-driven solution arises from personal needs as job seekers. Recognizing the importance of understanding fluctuating demand for technical skills, the proposed solution aims to provide quantitative insights, helping job seekers stay competitive in the evolving market.

### Objective:
Our information system aims to quantify changing skill demand, addressing a gap in understanding market needs. Unlike previous work, our innovative solution provides specific insights into evolving skills, aiding individual growth. Recognizing the importance of the employment index, our system can assist policymakers in timely workforce interventions for a healthy economy.

### Significance to real world:
Top economic policy researchers and consulting firms like McKinsey and Deloitte highlight significant shifts in skill demand due to automation, technology changes, and events like COVID-19. However, major job portals such as LinkedIn, Indeed, or Glassdoor lack analytical solutions for understanding these shifts. Our innovative solution provides granular insights into specific skill and tool demand changes, along with tracking shifts in employee perceptions post-external shocks like COVID-19, including phenomena like the great resignation and employee dissatisfaction with returning to the office.

### Project Workflow:
**Workflow 1**
Raw CSV data was processed and cleaned using Python's PySpark and Pandas. The processed data was stored in an Amazon S3 bucket on AWS, crawled to the Glue Data Catalog, and underwent ETL processes using Glue jobs. Finally, the data was loaded into Amazon Redshift for analysis through SQL queries in the Redshift Query Editor V2.

**Workflow 2**
The Skill attribute and related features were stored in a separate CSV file to adhere to First Normal Form. Using Python Pandas, essential attributes for the Neo4J data model were mapped to this file. After importing the updated CSV into Neo4J AuraDB, the data model was constructed. The Graph Database was connected to the GraphXR Platform for visual analytics using the Neo4J Data Model's API Connection String.

**Workflow 3**
Normalized and cleaned CSV data is imported into the MySQL server via MySQL Workbench. Connection to the MySQL server is established using the Python/MySQL connector from a Python application, facilitating data analysis through SQL queries in MySQL Workbench and Python code.

Workflow 1 and 3 were employed to reproduce the viable analytical solutions provided by established job portals in the market. Meanwhile, Workflow 2 was utilized to create one of our visual solutions, monitoring skill demand in the current job market.


