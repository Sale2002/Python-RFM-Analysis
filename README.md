# **[Python] RFM Analysis**
# **I. Introduction**
**Business Problem:** SuperStore, a global retail company, intends to launch marketing campaigns during the Christmas and New Year's seasons to express appreciation to existing customers and identify potential loyal customers.

=> As a data analyst, I have opted to apply RFM (Recency – Frequency – Monetary) analysis to segment the large customer base, facilitating the creation of targeted marketing strategies and personalized customer care programs.
# Why RFM?
* RFM (Recency, Frequency, Monetary) analysis is a marketing model using customer segmentation based on their transaction history.
* This model could be very useful, especially for small and medium-sized enterprises (SMEs) with limited marketing resources, helping them focus on the potentially right customer segments to increase ROI, reduce churn, reduce cost, improve customer relationship, and a lot more.
# How?
* In RFM analysis, customers are scored based on three factors (Recency - how recently, Frequency - how often, Monetary - how much), then labeled based on the combination of RFM scores.

**Reference:** https://www.putler.com/rfm-analysis
# II. Data Exploration & Data Processing
## 1. Data Information
This is a transnational data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.
* InvoiceNo: Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'C', it indicates a cancellation.
* StockCode: Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.
* Description: Product (item) name. Nominal.
* Quantity: The quantities of each product (item) per transaction. Numeric.
* InvoiceDate: Invoice Date and time. Numeric, the day and time when each transaction was generated.
* UnitPrice: Unit price. Numeric, Product price per unit in sterling.
* CustomerID: Customer number. Nominal, a 5-digit integral number uniquely assigned to each customer.
* Country: Country name. Nominal, the name of the country where each customer resides.
## 2. EDA 
**Overview data**
![image](https://github.com/user-attachments/assets/66d258f1-0486-4566-959b-b2f5cfb03085)
![image](https://github.com/user-attachments/assets/deec06f9-6111-4a4f-a3ab-49dbd2549da5)
![image](https://github.com/user-attachments/assets/d4341612-44aa-43f1-a32a-9ee0c9bd1153)

=> With the available data and context, it is impossible to impute values for ~140k rows where CustomerID is null. Therefore, we delete these rows from the dataframe in this situation; we also drop duplicate rows in this step.
![image](https://github.com/user-attachments/assets/d3c5d38d-e9c0-4881-aec3-108e993a77ee)
**Convert some columns to the potentially correct data type**
![image](https://github.com/user-attachments/assets/a0f4e713-6568-411f-914b-e86be6efafc2)
## 3. Data Processing
**Cancelled transactions can also be filtered by InvoiceNo starting with letter "C"**
![image](https://github.com/user-attachments/assets/3bb4b50a-f02e-4de9-8cf5-ee00f497b579)
![image](https://github.com/user-attachments/assets/5abe1544-cf25-4ff3-8aee-f10a08c15a47)
![image](https://github.com/user-attachments/assets/6dce9a39-8c04-4d70-8037-3c6578f73b4b)
![image](https://github.com/user-attachments/assets/fca70708-6150-4136-a2dd-bb7d57239527)
![image](https://github.com/user-attachments/assets/92d43352-0b0d-4f27-b32f-ebe2e0eaa1c2)
![image](https://github.com/user-attachments/assets/62c3fe09-a5b7-4abc-9dc0-261710f819ad)
![image](https://github.com/user-attachments/assets/65777038-ae03-4a99-b556-5a0b29772f2c)
![image](https://github.com/user-attachments/assets/c6eac96b-009c-4bbc-bb48-ae8a5c7d6dc9)
![image](https://github.com/user-attachments/assets/b1da8acb-88e6-408a-beba-dfccfad57af2)
=> Number of cancelled transactions: 16.47%. The quantity of cancellations is pretty large.
![image](https://github.com/user-attachments/assets/841a8e50-a047-40ac-adb7-10dcf9674923)
![image](https://github.com/user-attachments/assets/42893ce5-3235-43ae-91c2-84269ae8ca74)
![image](https://github.com/user-attachments/assets/259b5786-cd79-4d77-aea5-527a5b340737)
![image](https://github.com/user-attachments/assets/19539539-6227-4407-b157-1a84dc83656c)
![image](https://github.com/user-attachments/assets/1ff53303-0fea-4082-88b8-aaad19c589a0)
![image](https://github.com/user-attachments/assets/589623e1-6bd5-4127-97f0-99d1a711460d)
![image](https://github.com/user-attachments/assets/f4aceffe-cc36-458b-ba17-7325d1de9f74)
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
