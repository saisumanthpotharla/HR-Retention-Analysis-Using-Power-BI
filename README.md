# HR Retention Analysis Using Power BI

## Introduction
Welcome to my HR Retention Analysis project! This project utilizes a dataset from [data.world](https://data.world/) to explore employee retention and attrition within organizations. The goal is to uncover insights that can help HR professionals improve retention strategies and enhance workforce satisfaction.

## Project Overview
This analysis aims to identify key factors affecting employee retention and visualize the data using Power BI. The interactive dashboard enables users to explore various dimensions of employee data, facilitating a deeper understanding of retention trends.

## Dataset Description
The dataset includes the following key columns:

| Diverse      | Emp Satisfaction | Employee ID | Gender         | Gender ID | Hire Date  | Perf Score ID | Performance Score | POC or POC NA | Position     | Position ID | Race Desc | Race ID | Age | Attrition | Business Travel  | Department              | Education           | EducationField | JobRole              | MaritalStatus |
|--------------|------------------|-------------|----------------|-----------|------------|----------------|-------------------|----------------|--------------|-------------|-----------|---------|-----|-----------|-------------------|-------------------------|---------------------|----------------|----------------------|---------------|
| Non-Diverse  | 4                | 55-5555862  | Male & N/A     | 0         | 16-12-2017 | 1              | PIP               | Non-POC       | Vice President| 1           | White     | 1       | 41  | Yes       | Travel_Rarely     | Sales                   | Associates Degree    | Life Sciences  | Sales Executive      | Single        |
| Non-Diverse  | 4                | 41-2211365  | Male & N/A     | 0         | 28-05-2022 | 1              | PIP               | Non-POC       | Vice President| 1           | White     | 1       | 49  | No        | Travel_Frequently  | Research & Development  | High School         | Life Sciences  | Research Scientist   | Married       |
| Diverse      | 5                | 07-6503674  | Female         | 1         | 25-08-2022 | 1              | PIP               | Non-POC       | Vice President| 1           | White     | 1       | 37  | Yes       | Travel_Rarely     | Research & Development  | Associates Degree    | Other          | Laboratory Technician | Single        |
| Non-Diverse  | 4                | 34-3408841  | Male & N/A     | 0         | 12-05-2017 | 1              | PIP               | Non-POC       | Vice President| 1           | White     | 1       | 33  | No        | Travel_Frequently  | Research & Development  | Master's Degree      | Life Sciences  | Research Scientist   | Married       |
| Non-Diverse  | 3                | 39-5593292  | Male & N/A     | 0         | 22-04-2019 | 1              | PIP               | Non-POC       | Vice President| 1           | White     | 1       | 27  | No        | Travel_Rarely     | Research & Development  | High School         | Medical       | Laboratory Technician | Married       |

## Power BI Dashboard

### Overview Page
The overview page contains several visualizations that provide insights into employee retention:

- **Cards:** Displaying total retention, average age, and the most common education level.
- **Bar Graphs:** Comparing retention percentages across different departments, performance scores, and job roles.
- **Scatter Plot:** Showing the distribution of employees by gender and age.
- **Stacked Bar Chart:** Illustrating the relationship between business travel and age groups, with small multiples indicating marital status.

### Explore Page
The explore page allows users to interact with the data through various slicers, including:

- Year
- Department
- Age
- Gender
- Job Role
- Education
- Position

This functionality enables users to create a dynamic matrix tailored to their specific interests and analyze data in a customized way.

## DAX Measures
Here are some key DAX measures used in the project:

- **Retention Percentage:** 
    ```DAX
    Retention % = DIVIDE(SUM(hr[Retention]), SUM(hr[Employee Count]), 0)
    ```
- **Attrition Percentage:** 
    ```DAX
    Attrition % = DIVIDE(SUM(hr[Attrition]), SUM(hr[Employee Count]), 0)
    ```

Feel free to explore the DAX measures and customize them for your analysis!

## Conclusion
This HR retention analysis project highlights significant trends and factors that affect employee retention. By utilizing Power BI's interactive dashboard, HR professionals can gain valuable insights to improve employee satisfaction and retention strategies.

## Getting Started
To get started with this project:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/HR-Retention-Analysis.git
