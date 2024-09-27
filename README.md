# **[Python] RFM Analysis**
# **I. Introduction**
## 1.1. Project Overview: 
This project aims to assist SuperStore, a global **retail company**, in launching **effective marketing campaigns** for the Christmas and New Year's seasons. The primary goal is to **express appreciation to existing customers and identify potential loyal customers** for personalized engagement. By applying **RFM** (Recency, Frequency, Monetary) analysis, the project seeks to **segment the large customer base**, enabling the development of **targeted marketing strategies** and **customized customer care programs**. This approach helps SuperStore increase ROI, **reduce customer churn, optimize marketing expenses, and improve customer relationships**.

## 1.2. Business Problem: 
SuperStore needs to identify **key customer segments** to focus their marketing resources on the right groups, ensuring more effective outreach and personalized customer engagement during the holiday seasons. This involves determining which customers are most loyal, most active, and most profitable, allowing the business to allocate resources efficiently and improve customer satisfaction.

## 1.3 Solution Approach: 
The **RFM analysis model** is employed, which segments customers based on three factors:

* **Recency:** How recently a customer made a purchase.
* **Frequency:** How often the customer has made purchases.
* **Monetary:** How much the customer has spent overall.

By scoring customers on these dimensions, the company can create **meaningful customer segments**, such as high-value, inactive, or recent customers, and tailor marketing strategies for each segment.

**Reference:** https://www.putler.com/rfm-analysis
# II. Data Exploration & Data Processing
## 2.1. Data Information
This is a transnational data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.
* InvoiceNo: Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'C', it indicates a cancellation.
* StockCode: Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.
* Description: Product (item) name. Nominal.
* Quantity: The quantities of each product (item) per transaction. Numeric.
* InvoiceDate: Invoice Date and time. Numeric, the day and time when each transaction was generated.
* UnitPrice: Unit price. Numeric, Product price per unit in sterling.
* CustomerID: Customer number. Nominal, a 5-digit integral number uniquely assigned to each customer.
* Country: Country name. Nominal, the name of the country where each customer resides.
## 2.2. Data Exploration 
### 2.2.1. Loading and Initial Data Inspection:
![image](https://github.com/user-attachments/assets/138031db-776e-483b-ac83-a41c23e59d67)

**Function Used:**
* _pd.read_excel():_ Loads the data from an Excel file.
* _data.head():_ Displays the first five rows of the dataframe.
* _data.info():_ Provides information about the dataframe (data types, non-null counts).
* _data.shape:_ Returns the dimensions of the dataframe (rows, columns).

**Purpose:** To load and inspect the dataset structure before manipulation.
### 2.2.2. Data Cleaning:
After reviewing the data, we observed that a significant portion of the data **contained null values**. Therefore, we have decided on the following approach: given the available data and context, it is not feasible to impute values for approximately 140,000 rows where the CustomerID is null. As a result, we will **delete these rows** from the dataframe. Additionally, **duplicate rows will be removed** in this step as well.

![image](https://github.com/user-attachments/assets/ea5a87ad-cb2f-47cc-90b2-a2e672aee960)

**Function Used:**

* _dropna():_ Removes rows with missing values in the CustomerID column.
* _drop_duplicates():_ Removes duplicate rows.

**Purpose:** To clean the dataset by removing invalid or redundant rows.
### 2.2.3. Converting Data Types:
Convert some columns to the potentially correct data type

![image](https://github.com/user-attachments/assets/6571b9ad-f4ba-4a9f-948c-5aebf1fa5acc)

**Function Used:**

* _pd.to_datetime():_ Converts the InvoiceDate column to datetime format.
* _astype():_ Changes the data type of CustomerID to object.

**Purpose:** Ensures the correct data types for analysis.
## 2.3. Data Processing
### 2.3.1. Handling Cancellations:

![image](https://github.com/user-attachments/assets/2a255b8b-de92-4650-acf6-e2cc67ae59b8)

**Function Used:**

* _Filtering:_ data[data['Quantity'] < 0] filters out transactions where Quantity is negative (indicating cancellations).
* _Multiplication:_ Calculates the loss for canceled transactions (Quantity × UnitPrice).

**Purpose:** To isolate and calculate the loss from canceled transactions.
### 2.3.2. Aggregating Canceled Transactions:

![image](https://github.com/user-attachments/assets/18486b97-6f68-40b5-b8f9-29378e55a007)

**Function Used:**

* _groupby():_ Groups the data by InvoiceNo, Country, and CustomerID.
* _agg():_ Aggregates the grouped data by taking the maximum InvoiceDate and summing the Loss.
* _reset_index():_ Resets the index after the aggregation.

**Purpose:** To summarize canceled transactions by invoice and customer.
### 2.3.3. Handling Delivered Transactions:

![image](https://github.com/user-attachments/assets/66cf604e-7060-43a0-96af-7c86a2709264)

**Function Used:**

* _Filtering:_ data[data['Quantity'] >= 0] filters out transactions where Quantity is non-negative.
* _Multiplication:_ Calculates the revenue for delivered transactions (Quantity × UnitPrice).

**Purpose:** To isolate and calculate the revenue from delivered transactions.
# III. Data Visualization
![image](https://github.com/user-attachments/assets/777d3609-5afb-4ee1-8911-c1979f529b4f)
![image](https://github.com/user-attachments/assets/d5e3aafe-52dc-4a4a-8865-533384bd7d4b)
![image](https://github.com/user-attachments/assets/c7750823-9a0c-4977-b61a-cd1c847927bd)
![image](https://github.com/user-attachments/assets/dab9bad7-a55e-4686-a452-65fe14514a5b)
![image](https://github.com/user-attachments/assets/a7f5c4f4-c85e-48c8-901e-35425edef869)
![image](https://github.com/user-attachments/assets/6ceae8a7-e1a6-4fe1-a8f1-e55857d60cd6)
![image](https://github.com/user-attachments/assets/a25ac7d7-76c5-4feb-9ac3-e444bcb437b3)
![image](https://github.com/user-attachments/assets/00fa295e-62c7-4903-8ab8-de97cb46d0ac)
![image](https://github.com/user-attachments/assets/ed6f759d-db58-4f20-80c8-2226e8e2a42c)
# IV. Recommendation
![image](https://github.com/user-attachments/assets/2e0f8d48-1567-4422-b040-3dca049527e9)
