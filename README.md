# Employee Survey Data Processor

## Overview
This repository contains a Python-based solution for processing and analyzing employee survey data stored in a MySQL database. The project connects to a MySQL database, retrieves data from multiple tables, performs data aggregation, and inserts processed results into a target table. It also includes performance benchmarking for different sample sizes to evaluate scalability.

The codebase is implemented in a Jupyter Notebook, leveraging the mysql-connector-python library to interact with the database. It is designed to handle large datasets efficiently and provides insights into employee details, survey attributes, and results.

## Features

• **Database Connectivity:** Establishes a connection to a MySQL database using ``` mysql-connector-python ```.

• **Data Exploration:** Retrieves and displays table structures, total record counts, and sample data from five tables:

  1.  ```employee_name``` (53,248 records)

  2. ```survey_attribute``` (19 records)
  
  3. ```survey_report``` (30,825 records)

  4. ```survey_result``` (48,213 records)

  5. ```value_set``` (251 records)

• **Data Processing:** Aggregates employee details (ID, first name, last name) with survey-related data (absentee reasons, certifications) and inserts them into the survey_report table.

• **Performance Benchmarking:** Measures execution time for processing various sample sizes (100 to 30,825 records) to assess performance scalability.

• **Cleanup:** Truncates the survey_report table before inserting new data and properly closes database connection.


## Prerequisites

To run this project, ensure you have the following installed:

• Python 3.9+: The runtime environment for the scripts.

• MySQL Server: A running instance with the gp_06 database and required tables populated.


### Required Python Packages:

• ```mysql-connector-python``` 

• ```time``` (standard library, used for benchmarking)


### You can install the dependencies using:

 ```pip install mysql-connector-python```


## Limitations

1. The code assumes specific attribute IDs (e.g., ```absent_employee_reason_attr_id```, ```certifications_attr_id```) are defined elsewhere in the notebook (not shown in the truncated output). Ensure these variables are set correctly.

2. Performance may degrade with significantly larger datasets due to sequential querying.
3. Error handling is minimal; consider adding try-except blocks for production use.


## Future Improvements

1. Optimize queries using joins instead of sequential fetches to improve performance.

2. Add batch insertion for ```survey_report``` to reduce transaction overhead.
  
3. Implement logging and error handling for robustness.
   
4. Support configurable database credentials via environment variables or a config file.


## License

This project is licensed under the MIT License. See the LICENSE file for details.
