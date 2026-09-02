# Building-a-Retail-Sales-Data-Agent-on-Databricks
Retail Sales Data Agent built with Databricks for natural-language business insights.

# Building a Retail Sales Data Agent on Databricks

## Table of Contents

* [About the Project](#about-the-project)
* [Project Objective](#project-objective)
* [Dataset](#dataset)
* [Data Review and Preparation](#data-review-and-preparation)
* [Creating the Data Agent](#creating-the-data-agent)
* [Agent Instructions](#agent-instructions)
* [Testing the Data Agent](#testing-the-data-agent)

  * [Question 1 – Total Revenue](#question-1--total-revenue)
  * [Question 2 – Highest Sales by Product Category](#question-2--highest-sales-by-product-category)
  * [Question 3 – Sales by Gender](#question-3--sales-by-gender)
  * [Question 4 – Highest Sales Day](#question-4--highest-sales-day)
  * [Question 5 – Customer Purchase Behaviour](#question-5--customer-purchase-behaviour)
  * [Question 6 – Monthly Sales](#question-6--monthly-sales)
  * [Question 7 – Product Category Among Older Customers](#question-7--product-category-among-older-customers)
  * [Question 8 – Total Items Sold](#question-8--total-items-sold)
  * [Question 9 – Additional Business Question](#question-9--additional-business-question)
  * [Question 10 – Additional Business Question](#question-10--additional-business-question)
* [Validation of Agent Answers](#validation-of-agent-answers)

  * [Validation 1 – Total Revenue](#validation-1--total-revenue)
  * [Validation 2 – Sales by Gender](#validation-2--sales-by-gender)
  * [Validation 3 – Product Category](#validation-3--product-category)
* [Key Insights](#key-insights)
* [Business Recommendations](#business-recommendations)
* [Tools Used](#tools-used)
* [Project Structure](#project-structure)
* [Conclusion](#conclusion)
* [Author](#author)

---

## About the Project

This project focuses on building a **Retail Sales Data Agent using Databricks** and a retail sales transaction dataset.

The purpose of the project is to create an agent that can answer business questions about a shop's sales performance using the available data. Instead of manually analysing the dataset for every question, the Data Agent allows a business user to ask questions in plain language and receive answers based on the underlying retail sales data.

The project follows an end-to-end process that includes uploading and reviewing the dataset, preparing the data as a table, creating and configuring the Data Agent, testing the agent with business questions, and independently validating selected answers.

The project demonstrates how **data analytics and AI can be combined** to make retail sales information easier to explore and understand.

---

## Project Objective

The main objective of this project is to build a working **Retail Sales Data Agent in Databricks** using the retail sales dataset.

The Data Agent is designed to help business users, managers and decision-makers understand different aspects of the shop's performance, including:

* Overall sales performance
* Customer behaviour
* Product category performance
* Changes in sales over time
* Customer and product characteristics
* Transaction values
* Business-related questions based on the available data

Another important objective is to test how well the agent handles different types of questions and to independently check whether its answers are supported by the original dataset.

---

## Dataset

The project uses a retail sales transaction dataset.

The dataset was registered in Databricks as:

```text
retail_sales_data
```

Each row represents a retail transaction and contains information about the customer, product, quantity, price and total transaction value.

### Dataset Columns

| Column               | Description                            |
| -------------------- | -------------------------------------- |
| **Transaction ID**   | Unique identifier for a transaction    |
| **Date**             | Date on which the transaction occurred |
| **Customer ID**      | Identifier for the customer            |
| **Gender**           | Gender recorded for the customer       |
| **Age**              | Age of the customer                    |
| **Product Category** | Category of the product purchased      |
| **Quantity**         | Number of units purchased              |
| **Price per Unit**   | Price of one unit of the product       |
| **Total Amount**     | Total value of the transaction         |

The dataset contains **1,000 transactions** and was used as the main source of information for the Data Agent.

---

## Data Review and Preparation

Before creating the Data Agent, the dataset was reviewed in Databricks to understand its structure and identify any possible data-quality issues.

The review included:

* Checking column names
* Checking data types
* Reviewing sample records
* Checking for missing values
* Checking for unusual values
* Checking for possible negative quantities
* Reviewing age values
* Identifying fields that could be used for sales, customer and product analysis

The dataset was then prepared as the `retail_sales_data` table in Databricks.

Descriptions were added to the table and its columns to make the information easier for the Data Agent to understand and use.

---

## Creating the Data Agent

After preparing the dataset, a Data Agent was created in Databricks and connected to the:

```text
retail_sales_data
```

table.

A basic connectivity test was performed before moving to the main testing stage.

### Initial Connectivity Test

**Question:**

```text
How many rows are in the table?
```

**Agent Answer:**

```text
The retail sales dataset contains 1000 rows of transaction data.
```

This confirmed that the Data Agent could access the prepared dataset.

---

## Agent Instructions

The Data Agent was given specific instructions describing its role, the type of information it should use and how it should respond to business questions.

The instructions defined the agent as a **Retail Sales Data Agent** that helps business users, managers and CEOs understand the shop's sales performance.

The main rules included:

* Use only information available in the retail sales dataset.
* Do not make up information or guess answers.
* Answer questions related to sales, customers, products and trends.
* Include totals, averages, counts or percentages where relevant.
* Display monetary values in South African Rand (R).
* Use two decimal places for monetary values.
* Briefly explain what the results mean.

The instructions were designed to make the responses useful for business users while keeping the answers connected to the underlying dataset.

---

# Testing the Data Agent

After creating the Data Agent and adding the instructions, it was tested using business questions covering different areas of the dataset.

The questions focused on:

* Overall sales
* Product categories
* Customers
* Gender
* Age groups
* Time-based sales trends
* Transaction values
* Customer purchasing behaviour
* Business-related insights

The testing process was used to determine whether the agent could answer both simple questions and questions requiring multiple fields from the dataset.

---

## Question 1 – Total Revenue

**Question:**

```text
What is the total revenue across all transactions?
```

**Agent Answer:**

```text
R 456,000
```

The result provides an overall view of the revenue generated across the transactions in the dataset.

---

## Question 2 – Highest Sales by Product Category

**Question:**

```text
Which product category generated the highest total sales?
```

**Agent Answer:**

```text
Electronics generated the highest total sales.
```

The agent reported:

| Product Category | Total Sales | Percentage of Revenue | Transactions |
| ---------------- | ----------: | --------------------: | -----------: |
| Electronics      | R156,905.00 |                34.41% |          342 |
| Clothing         | R155,580.00 |                34.12% |          351 |
| Beauty           | R143,515.00 |                31.47% |          307 |

Electronics generated the highest sales, although the difference between Electronics and Clothing was relatively small.

---

## Question 3 – Sales by Gender

**Question:**

```text
How do total sales compare between male and female customers?
```

**Agent Answer:**

```text
Female customers generated slightly higher total sales.
```

The agent reported:

| Gender | Total Sales | Share of Revenue |
| ------ | ----------: | ---------------: |
| Female | R232,840.00 |           51.06% |
| Male   | R223,160.00 |           48.94% |

Female customers generated R9,680 more in sales than male customers.

---

## Question 4 – Highest Sales Day

**Question:**

```text
Which day had the most sales?
```

**Agent Answer:**

```text
May 23, 2023 had the highest sales.
```

The agent reported that May 23, 2023 recorded:

```text
Sales: R8,455.00
Transactions: 9
Average transaction value: R939.44
```

This was the highest single-day sales value identified in the analysis.

---

## Question 5 – Customer Purchase Behaviour

**Question:**

```text
How many items does a customer typically purchase?
```

**Agent Answer:**

```text
Customers typically purchase 2–3 items per transaction.
```

The agent reported:

* Average quantity per transaction: **2.5 items**
* Median quantity: **3 items**
* Minimum: **1 item**
* Maximum: **4 items**

This provides an indication of typical customer purchasing behaviour.

---

## Question 6 – Monthly Sales

**Question:**

```text
How many sales happened each month?
```

**Agent Answer:**

```text
Monthly sales ranged from 65 to 105 transactions.
```

May 2023 recorded the highest number of transactions with **105**, while September 2023 recorded the lowest with **65 transactions**.

This shows that sales activity varied throughout the year.

---

## Question 7 – Product Category Among Older Customers

**Question:**

```text
Which product category is most popular with older customers?
```

**Agent Answer:**

```text
Clothing is the most popular product category among older customers.
```

For customers aged **55+**, the agent reported:

| Product Category | Transactions | Percentage |
| ---------------- | -----------: | ---------: |
| Clothing         |           80 |     37.04% |
| Electronics      |           74 |     34.26% |
| Beauty           |           62 |     28.70% |

Clothing was therefore the most frequently purchased category among this age group.

---

## Question 8 – Total Items Sold

**Question:**

```text
How many items were sold altogether?
```

**Agent Answer:**

```text
2,514 items were sold altogether.
```

Across the 1,000 transactions, a total of **2,514 items** were sold.

The average quantity was approximately **2.51 items per transaction**.

---

## Question 9 – Additional Business Question

**Question:**

```text
What is the average transaction value for each product category, and which category has the highest average transaction value?
```

**Agent Answer:**

```text
[Insert the actual Data Agent answer here]
```

This question was designed to test whether the agent could calculate and compare transaction values across product categories.

> **Note:** Replace the answer above with the actual answer produced by the Data Agent after testing.

---

## Question 10 – Additional Business Question

**Question:**

```text
Which product category generated the most sales among customers aged 18 to 29, and how much did they spend?
```

**Agent Answer:**

```text
[Insert the actual Data Agent answer here]
```

This question combines **age, product category and sales value** to test whether the agent can answer a more detailed business question.

> **Note:** Replace the answer above with the actual answer produced by the Data Agent after testing.

---

# Validation of Agent Answers

Three of the Data Agent's answers were independently checked against the source data.

The purpose of the validation was to make sure that the agent's answers were supported by the underlying dataset rather than accepting the responses simply because they appeared reasonable.

The validation used techniques such as:

* Python calculations
* Grouping and aggregation
* Filtering
* Comparing calculated values with the agent's responses

---

## Validation 1 – Total Revenue

**Question:**

```text
What is the total revenue?
```

**Agent Answer:**

```text
R456,000
```

**Independent calculation:**

```python
rs["Total Amount"].sum()
```

**Verdict:**

```text
Correct
```

The independent calculation produced the same total revenue as the Data Agent.

---

## Validation 2 – Sales by Gender

**Question:**

```text
How do total sales compare between male and female customers?
```

**Agent Answer:**

```text
Female: R232,840
Male: R223,160
```

**Independent calculation:**

```python
rs.groupby('Gender')['Total Amount'].sum()
```

**Verdict:**

```text
Correct
```

The independent calculation matched the values provided by the Data Agent.

---

## Validation 3 – Highest-Selling Product Category

**Question:**

```text
Which product category generated the highest total sales?
```

**Agent Answer:**

```text
Electronics generated the highest total sales.
```

**Verdict:**

```text
Correct
```

The source data confirmed that Electronics generated the highest total sales among the three product categories.

---

# Key Insights

The testing and analysis of the retail sales dataset produced several useful insights about the shop's performance.

### Product Performance

Electronics generated the highest total sales at **R156,905.00**, followed closely by Clothing at **R155,580.00**.

The difference between the two categories was only **R1,325**, meaning that small changes in sales performance could change the ranking.

### Customer Gender

Female customers generated slightly more revenue than male customers.

Female customers accounted for **51.06%** of total revenue compared with **48.94%** for male customers.

The difference was relatively small, showing that sales were fairly balanced between the two groups.

### Age Groups

The analysis showed differences in spending behaviour between age groups.

The **45–54 age group** contributed the highest total sales, while younger age groups showed different purchasing patterns and average transaction values.

### Monthly Performance

May 2023 was the strongest month based on transaction volume, with **105 transactions**.

September 2023 recorded the lowest number of transactions, with **65**.

This difference suggests that there may be seasonal or operational factors affecting sales performance.

### Customer Purchasing Behaviour

Customers purchased an average of **2.5 items per transaction**, with the median transaction containing **3 items**.

### Product Preferences

Clothing was particularly popular among younger customers, while Electronics led overall in total revenue.

### Data Quality

The dataset review found:

* No missing values
* No negative quantities
* Ages within the expected range of 18–64
* Total Amount consistently matching Quantity × Price per Unit

This provided a reliable dataset for the Data Agent to analyse.

---

# Business Recommendations

Based on the findings from the analysis, several recommendations can be considered.

### 1. Target Younger Customers with Clothing Promotions

Clothing is already a popular category among younger customers. The business could consider targeted promotions aimed at customers in the **18–29 age group**.

### 2. Investigate the September Sales Decline

September recorded the lowest number of transactions. The business should investigate possible reasons such as:

* Stock availability
* Reduced marketing activity
* Seasonal demand
* Changes in customer behaviour

### 3. Monitor Electronics and Clothing Performance

Electronics and Clothing generated almost the same amount of revenue. Management should monitor both categories closely and focus on the category offering the stronger combination of sales and profitability.

### 4. Develop Loyalty or Upselling Strategies

The higher-value customer groups could be targeted with loyalty programmes or upselling strategies to encourage repeat purchases and increase customer value.

---

# Tools Used

The following tools and technologies were used in the project:

* **Databricks** – Data preparation and Data Agent development
* **Python** – Independent validation and data analysis
* **Pandas** – Data aggregation and validation
* **GitHub** – Project documentation and version control
* **Microsoft Word** – Project write-up and documentation

---

# Project Structure

The final repository can be organised as follows:

```text
Retail-Sales-Data-Agent/
│
├── README.md
│
├── Building_a_Retail_Sales_Data_Agent_on_Databricks.docx
│
├── data/
│   └── retail_sales_data.csv
│
└── screenshots/
    ├── dataset-upload.png
    ├── dataset-preview.png
    ├── dataset-schema.png
    ├── prepared-table.png
    ├── agent-setup.png
    ├── agent-instructions.png
    ├── question-01.png
    ├── question-02.png
    ├── question-03.png
    ├── question-04.png
    ├── question-05.png
    ├── question-06.png
    ├── question-07.png
    ├── question-08.png
    ├── question-09.png
    ├── question-10.png
    └── validation/
        ├── validation-01.png
        ├── validation-02.png
        └── validation-03.png
```

The exact folder structure may differ depending on the files included in the final repository.

---

# Conclusion

This project provided practical experience in building and testing a Data Agent using Databricks.

The project involved preparing a retail sales dataset, connecting it to a Data Agent, creating instructions for how the agent should work with the data, testing the agent with business questions and independently validating selected answers.

One of the most important lessons from the project was that an AI-generated answer should not automatically be treated as correct. The validation stage made it possible to compare the agent's responses with the underlying data and determine whether the answers were supported by evidence.

The project demonstrates how a Data Agent can make retail sales data easier to explore through natural-language questions while also showing the importance of understanding the data and independently checking AI-generated results.

---

# Author

**TOBANI KANISE**

Data Analytics | Business & Data Analysis | Agricultural Economics

---

## Project Repository

GitHub Repository:

**[Add your GitHub repository link here]**
