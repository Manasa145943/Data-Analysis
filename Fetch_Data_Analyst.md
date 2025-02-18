```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

```

# Loading CSV Files


```python
users_df = pd.read_csv("data/USER_TAKEHOME.csv")
transactions_df = pd.read_csv("data/TRANSACTION_TAKEHOME.csv")
products_df = pd.read_csv("data/PRODUCTS_TAKEHOME.csv")



```


```python
users_df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>CREATED_DATE</th>
      <th>BIRTH_DATE</th>
      <th>STATE</th>
      <th>LANGUAGE</th>
      <th>GENDER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5ef3b4f17053ab141787697d</td>
      <td>2020-06-24 20:17:54.000 Z</td>
      <td>2000-08-11 00:00:00.000 Z</td>
      <td>CA</td>
      <td>es-419</td>
      <td>female</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5ff220d383fcfc12622b96bc</td>
      <td>2021-01-03 19:53:55.000 Z</td>
      <td>2001-09-24 04:00:00.000 Z</td>
      <td>PA</td>
      <td>en</td>
      <td>female</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6477950aa55bb77a0e27ee10</td>
      <td>2023-05-31 18:42:18.000 Z</td>
      <td>1994-10-28 00:00:00.000 Z</td>
      <td>FL</td>
      <td>es-419</td>
      <td>female</td>
    </tr>
    <tr>
      <th>3</th>
      <td>658a306e99b40f103b63ccf8</td>
      <td>2023-12-26 01:46:22.000 Z</td>
      <td>NaN</td>
      <td>NC</td>
      <td>en</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>653cf5d6a225ea102b7ecdc2</td>
      <td>2023-10-28 11:51:50.000 Z</td>
      <td>1972-03-19 00:00:00.000 Z</td>
      <td>PA</td>
      <td>en</td>
      <td>female</td>
    </tr>
  </tbody>
</table>
</div>




```python
transactions_df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>RECEIPT_ID</th>
      <th>PURCHASE_DATE</th>
      <th>SCAN_DATE</th>
      <th>STORE_NAME</th>
      <th>USER_ID</th>
      <th>BARCODE</th>
      <th>FINAL_QUANTITY</th>
      <th>FINAL_SALE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0000d256-4041-4a3e-adc4-5623fb6e0c99</td>
      <td>2024-08-21</td>
      <td>2024-08-21 14:19:06.539 Z</td>
      <td>WALMART</td>
      <td>63b73a7f3d310dceeabd4758</td>
      <td>1.530001e+10</td>
      <td>1.00</td>
      <td></td>
    </tr>
    <tr>
      <th>1</th>
      <td>0001455d-7a92-4a7b-a1d2-c747af1c8fd3</td>
      <td>2024-07-20</td>
      <td>2024-07-20 09:50:24.206 Z</td>
      <td>ALDI</td>
      <td>62c08877baa38d1a1f6c211a</td>
      <td>NaN</td>
      <td>zero</td>
      <td>1.49</td>
    </tr>
    <tr>
      <th>2</th>
      <td>00017e0a-7851-42fb-bfab-0baa96e23586</td>
      <td>2024-08-18</td>
      <td>2024-08-19 15:38:56.813 Z</td>
      <td>WALMART</td>
      <td>60842f207ac8b7729e472020</td>
      <td>7.874223e+10</td>
      <td>1.00</td>
      <td></td>
    </tr>
    <tr>
      <th>3</th>
      <td>000239aa-3478-453d-801e-66a82e39c8af</td>
      <td>2024-06-18</td>
      <td>2024-06-19 11:03:37.468 Z</td>
      <td>FOOD LION</td>
      <td>63fcd7cea4f8442c3386b589</td>
      <td>7.833997e+11</td>
      <td>zero</td>
      <td>3.49</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00026b4c-dfe8-49dd-b026-4c2f0fd5c6a1</td>
      <td>2024-07-04</td>
      <td>2024-07-05 15:56:43.549 Z</td>
      <td>RANDALLS</td>
      <td>6193231ae9b3d75037b0f928</td>
      <td>4.790050e+10</td>
      <td>1.00</td>
      <td></td>
    </tr>
  </tbody>
</table>
</div>




```python
products_df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CATEGORY_1</th>
      <th>CATEGORY_2</th>
      <th>CATEGORY_3</th>
      <th>CATEGORY_4</th>
      <th>MANUFACTURER</th>
      <th>BRAND</th>
      <th>BARCODE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Health &amp; Wellness</td>
      <td>Sexual Health</td>
      <td>Conductivity Gels &amp; Lotions</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.964944e+11</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Snacks</td>
      <td>Puffed Snacks</td>
      <td>Cheese Curls &amp; Puffs</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.327801e+10</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Health &amp; Wellness</td>
      <td>Hair Care</td>
      <td>Hair Care Accessories</td>
      <td>NaN</td>
      <td>PLACEHOLDER MANUFACTURER</td>
      <td>ELECSOP</td>
      <td>4.618178e+11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Health &amp; Wellness</td>
      <td>Oral Care</td>
      <td>Toothpaste</td>
      <td>NaN</td>
      <td>COLGATE-PALMOLIVE</td>
      <td>COLGATE</td>
      <td>3.500047e+10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Health &amp; Wellness</td>
      <td>Medicines &amp; Treatments</td>
      <td>Essential Oils</td>
      <td>NaN</td>
      <td>MAPLE HOLISTICS AND HONEYDEW PRODUCTS INTERCHA...</td>
      <td>MAPLE HOLISTICS</td>
      <td>8.068109e+11</td>
    </tr>
  </tbody>
</table>
</div>



# 1. Checking Data Quality


```python
print("Users Dataset Info:")
print(users_df.info())
print("\nMissing Values in Users Dataset:")
print(users_df.isnull().sum())

print("\nTransactions Dataset Info:")
print(transactions_df.info())
print("\nMissing Values in Transactions Dataset:")
print(transactions_df.isnull().sum())

print("\nProducts Dataset Info:")
print(products_df.info())
print("\nMissing Values in Products Dataset:")
print(products_df.isnull().sum())

```

    Users Dataset Info:
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 100000 entries, 0 to 99999
    Data columns (total 6 columns):
     #   Column        Non-Null Count   Dtype 
    ---  ------        --------------   ----- 
     0   ID            100000 non-null  object
     1   CREATED_DATE  100000 non-null  object
     2   BIRTH_DATE    96325 non-null   object
     3   STATE         95188 non-null   object
     4   LANGUAGE      69492 non-null   object
     5   GENDER        94108 non-null   object
    dtypes: object(6)
    memory usage: 4.6+ MB
    None
    
    Missing Values in Users Dataset:
    ID                  0
    CREATED_DATE        0
    BIRTH_DATE       3675
    STATE            4812
    LANGUAGE        30508
    GENDER           5892
    dtype: int64
    
    Transactions Dataset Info:
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 50000 entries, 0 to 49999
    Data columns (total 8 columns):
     #   Column          Non-Null Count  Dtype  
    ---  ------          --------------  -----  
     0   RECEIPT_ID      50000 non-null  object 
     1   PURCHASE_DATE   50000 non-null  object 
     2   SCAN_DATE       50000 non-null  object 
     3   STORE_NAME      50000 non-null  object 
     4   USER_ID         50000 non-null  object 
     5   BARCODE         44238 non-null  float64
     6   FINAL_QUANTITY  50000 non-null  object 
     7   FINAL_SALE      50000 non-null  object 
    dtypes: float64(1), object(7)
    memory usage: 3.1+ MB
    None
    
    Missing Values in Transactions Dataset:
    RECEIPT_ID           0
    PURCHASE_DATE        0
    SCAN_DATE            0
    STORE_NAME           0
    USER_ID              0
    BARCODE           5762
    FINAL_QUANTITY       0
    FINAL_SALE           0
    dtype: int64
    
    Products Dataset Info:
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 845552 entries, 0 to 845551
    Data columns (total 7 columns):
     #   Column        Non-Null Count   Dtype  
    ---  ------        --------------   -----  
     0   CATEGORY_1    845441 non-null  object 
     1   CATEGORY_2    844128 non-null  object 
     2   CATEGORY_3    784986 non-null  object 
     3   CATEGORY_4    67459 non-null   object 
     4   MANUFACTURER  619078 non-null  object 
     5   BRAND         619080 non-null  object 
     6   BARCODE       841527 non-null  float64
    dtypes: float64(1), object(6)
    memory usage: 45.2+ MB
    None
    
    Missing Values in Products Dataset:
    CATEGORY_1         111
    CATEGORY_2        1424
    CATEGORY_3       60566
    CATEGORY_4      778093
    MANUFACTURER    226474
    BRAND           226472
    BARCODE           4025
    dtype: int64
    


```python

```

# 2. converting Date Cloumns to Datetime

# 2.1.converting date columns in users dataset


```python
users_df["CREATED_DATE"] = pd.to_datetime(users_df["CREATED_DATE"], errors="coerce")
users_df["BIRTH_DATE"] = pd.to_datetime(users_df["BIRTH_DATE"], errors="coerce")

```

# 2.2.converting date columns to transcations dataset



```python
transactions_df["PURCHASE_DATE"] = pd.to_datetime(transactions_df["PURCHASE_DATE"], errors="coerce")
transactions_df["SCAN_DATE"] = pd.to_datetime(transactions_df["SCAN_DATE"], errors="coerce")

```

# 3.Fixing Final_Quality and Final_Sale

# 3.1. Converting Final_Quality to Numeric


```python
transactions_df["FINAL_QUANTITY"] = transactions_df["FINAL_QUANTITY"].replace("zero", 0).astype(float)

```

# 3.2. Coverting Final_Sale to Numeric


```python
transactions_df["FINAL_SALE"] = pd.to_numeric(transactions_df["FINAL_SALE"], errors="coerce").fillna(0)

```

# 4.Handling Missing Values

# 4.1. Filling Missing Values in Users Dataset


```python
users_df["LANGUAGE"].fillna("unknown", inplace=True)
users_df["GENDER"].fillna("unknown", inplace=True)

```

# 4.2. Handling Missing Values in Product Dataset


```python
products_df["MANUFACTURER"].replace("PLACEHOLDER MANUFACTURER", np.nan, inplace=True)
products_df["BRAND"].replace("REM BRAND", np.nan, inplace=True)

products_df["CATEGORY_4"].fillna("unknown", inplace=True)

```

# 5.Identifing Duplicates

#  5.1. Checking for Duplicate users


```python
print("Duplicate Users:", users_df.duplicated().sum())

```

    Duplicate Users: 0
    

# 5.2. Checking for Duplicate receipts in transactions


```python
print("Duplicate Receipts:", transactions_df["RECEIPT_ID"].duplicated().sum())

```

    Duplicate Receipts: 25560
    

# 5.3 Checking for Duplicate Barcode in Products

# 5.3. Duplicates exists, so removing the duplicates


```python
print ("Duplicate Barcodes:", products_df["BARCODE"].duplicated().sum())
```

    Duplicate Barcodes: 4209
    


```python
users_df.drop_duplicates(inplace=True)
transactions_df.drop_duplicates(subset="RECEIPT_ID", inplace=True)
products_df.drop_duplicates(subset="BARCODE", inplace=True)

```

# 6.Data Visualization 

# 6.1. Missing Values Heatmap


```python
plt.figure(figsize=(12, 6))
sns.heatmap(users_df.isnull(), cmap="viridis", cbar=False)
plt.title("Missing Values in Users Dataset")
plt.show()

```


    
![png](output_35_0.png)
    



```python
plt.figure(figsize=(12, 6))
sns.heatmap(transactions_df.isnull(), cmap="viridis", cbar=False)
plt.title("Missing Values in Transactions Dataset")
plt.show()
```


    
![png](output_36_0.png)
    



```python
plt.figure(figsize=(12, 6))
sns.heatmap(products_df.isnull(), cmap="viridis", cbar=False)
plt.title("Missing Values in Products Dataset")
plt.show()
```


    
![png](output_37_0.png)
    


# Distribution of FINAL_SALE values


```python
plt.figure(figsize=(8,5))
sns.boxplot(x=transactions_df["FINAL_SALE"])
plt.title("Distribution of Final Sales")
plt.show()

```


    
![png](output_39_0.png)
    


# 6.2. Top 10 Brands by Number of Transactions


```python
top_brands = transactions_df.merge(products_df, on="BARCODE", how="left")["BRAND"].value_counts().head(10)

plt.figure(figsize=(10, 5))
top_brands.plot(kind="bar")
plt.title("Top 10 Brands by Number of Transactions")
plt.xlabel("Brand")
plt.ylabel("Transaction Count")
plt.show()

```


    
![png](output_41_0.png)
    


# 7.Save the Cleaned Data


```python
users_df.to_csv("data/cleaned_users.csv", index=False)
transactions_df.to_csv("data/cleaned_transactions.csv", index=False)
products_df.to_csv("data/cleaned_products.csv", index=False)

```

# Data Quality issues identified
1. Missing Brand Data
Issue: Many transactions are missing values in the BRAND field.
For Example
Snacks Category: 261 transactions missing BRAND.
Health & Wellness Category: 121 transactions missing BRAND.

2. High Percentage of Duplicate Receipts
Issue: Around 25,560 duplicate receipts were found, accounting for 50% of transactions.
Users scanning the same receipt multiple times.
Data processing error leading to duplicate entries.

3. Missing User Demographic Data
Issue: 3,675 users (~3.7%) are missing BIRTH_DATE, making age-based segmentation less reliable.
For Example
Users without BIRTH_DATE are excluded from age-based insights.

4. Unmapped Barcodes in the products Table
Issue: 4,209 barcodes are present without product descriptions.

# Fields That Are Challenging to Understand
1. FINAL_SALE vs. TOTAL_AMOUNT
FINAL_SALE represents final purchase value after discounts.
TOTAL_AMOUNT might refer to the pre-discount amount.

2. CATEGORY_1, CATEGORY_2, CATEGORY_3, CATEGORY_4
Issue: The dataset has multiple category levels, but the relationship between them is unclear.
For Example
CATEGORY_1 = Snacks, CATEGORY_2 = Chips, CATEGORY_3 = None, CATEGORY_4 = None

3. USER_ID Formatting
Issue: USER_ID is stored as a long alphanumeric string (e.g., 630789e1101ae272a4852287).
Impact:
Hard to track user activity or segment users without additional metadata (e.g., user type, signup date).
Suggested Fix:
Fetch’s database may need an additional user_profile table for segmentation.



# SQL Queries

# Close-ended Questions


```python
import sqlite3

# Create an in-memory SQLite database
conn = sqlite3.connect(":memory:")
cursor = conn.cursor()

```


```python
conn = sqlite3.connect("fetch_data.db")  # Saves to a file

```


```python
# Load Data into SQLite
users_df.to_sql("users", conn, if_exists="replace", index=False)
transactions_df.to_sql("transactions", conn, if_exists="replace", index=False)
products_df.to_sql("products", conn, if_exists="replace", index=False)

print("Data successfully loaded into SQLite.")
```

    Data successfully loaded into SQLite.
    

# Query 1: Top 5 Brands by Receipts Scanned (Users 21+)

Goal:
Identify the top 5 brands based on the number of receipts scanned by users aged 21 and older.

Assumptions:
Users must be 21 years or older → Age is calculated using BIRTH_DATE.
Sales are counted based on the number of receipts scanned (RECEIPT_ID).
Brands are identified using the BRAND column from the products table.
Transactions without valid user data are ignored (if BIRTH_DATE is missing, the user is excluded).
Ties are handled by ordering alphabetically after count ranking.


```python
query = """
SELECT p.BRAND, COUNT(t.RECEIPT_ID) AS receipts_scanned
FROM transactions t
JOIN users u ON t.USER_ID = u.ID
JOIN products p ON t.BARCODE = p.BARCODE
WHERE (strftime('%Y', 'now') - strftime('%Y', u.BIRTH_DATE)) >= 21
GROUP BY p.BRAND
ORDER BY receipts_scanned DESC
LIMIT 5;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>BRAND</th>
      <th>receipts_scanned</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NERDS CANDY</td>
      <td>6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>DOVE</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>None</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>TRIDENT</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>SOUR PATCH KIDS</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>



# Query 2: What is the percentage of sales in the Health & Wellness category by generation?

Goal:
Determine the percentage of total sales that comes from the Health & Wellness category, grouped by generation.


Assumptions:
Sales are measured using FINAL_SALE (total revenue).
Generations are categorized based on BIRTH_DATE:
Gen Z: Born 1997 or later (Age ≤ 26 in 2024)
Millennials: Born 1981-1996 (Age 27-42 in 2024)
Gen X: Born 1965-1980 (Age 43-58 in 2024)
Boomers: Born 1946-1964 (Age 59-78 in 2024)
Silent Gen: Born before 1946 (Age ≥ 79 in 2024)
Users without BIRTH_DATE will be excluded.
The CATEGORY_1 column in the products table contains "Health & Wellness" products.



```python
query = """
WITH user_generations AS (
    SELECT ID AS user_id,
           CASE 
               WHEN strftime('%Y', 'now') - strftime('%Y', BIRTH_DATE) <= 26 THEN 'Gen Z'
               WHEN strftime('%Y', 'now') - strftime('%Y', BIRTH_DATE) BETWEEN 27 AND 42 THEN 'Millennials'
               WHEN strftime('%Y', 'now') - strftime('%Y', BIRTH_DATE) BETWEEN 43 AND 58 THEN 'Gen X'
               WHEN strftime('%Y', 'now') - strftime('%Y', BIRTH_DATE) BETWEEN 59 AND 78 THEN 'Boomers'
               WHEN strftime('%Y', 'now') - strftime('%Y', BIRTH_DATE) >= 79 THEN 'Silent Gen'
           END AS generation
    FROM users
    WHERE BIRTH_DATE IS NOT NULL
),
health_sales AS (
    SELECT u.generation, 
           SUM(t.FINAL_SALE) AS health_wellness_sales
    FROM transactions t
    JOIN user_generations u ON t.USER_ID = u.user_id
    JOIN products p ON t.BARCODE = p.BARCODE
    WHERE p.CATEGORY_1 = 'Health & Wellness'
    GROUP BY u.generation
),
total_sales AS (
    SELECT u.generation, 
           SUM(t.FINAL_SALE) AS total_sales
    FROM transactions t
    JOIN user_generations u ON t.USER_ID = u.user_id
    GROUP BY u.generation
)
SELECT h.generation, 
       h.health_wellness_sales, 
       t.total_sales, 
       (h.health_wellness_sales * 100.0) / t.total_sales AS health_sales_percentage
FROM health_sales h
JOIN total_sales t ON h.generation = t.generation
ORDER BY health_sales_percentage DESC;
"""

pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>generation</th>
      <th>health_wellness_sales</th>
      <th>total_sales</th>
      <th>health_sales_percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Boomers</td>
      <td>91.91</td>
      <td>334.76</td>
      <td>27.455491</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Gen X</td>
      <td>61.57</td>
      <td>271.35</td>
      <td>22.690252</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Millennials</td>
      <td>36.18</td>
      <td>267.95</td>
      <td>13.502519</td>
    </tr>
  </tbody>
</table>
</div>



# Open-ended questions

# Query 3: Fetch’s Power Users

Goal: Identify Fetch’s most active users.

Assumptions:
Power users are top 5 users who scanned the most receipts.
We count distinct transactions per user.


```python
query = """
SELECT u.ID AS user_id, COUNT(t.RECEIPT_ID) AS total_receipts
FROM transactions t
JOIN users u ON t.USER_ID = u.ID
GROUP BY u.ID
ORDER BY total_receipts DESC
LIMIT 5;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>user_id</th>
      <th>total_receipts</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>6528a0a388a3a884364d94dc</td>
      <td>6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>646bdaa67a342372c857b958</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>62ffec490d9dbaff18c0a999</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>62c09104baa38d1a1f6c260e</td>
      <td>6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>61a58ac49c135b462ccddd1c</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```

# Additional queries to understand the data 

# To identify the top 5 most purchased products, based on barcode transactions.




```python
query = """
SELECT p.BARCODE, 
       COUNT(t.RECEIPT_ID) AS total_purchases
FROM transactions t
JOIN products p ON t.BARCODE = p.BARCODE
GROUP BY p.BARCODE
ORDER BY total_purchases DESC
LIMIT 5;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>BARCODE</th>
      <th>total_purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.111115e+11</td>
      <td>168</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5.111110e+11</td>
      <td>164</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3.111112e+11</td>
      <td>150</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.900000e+10</td>
      <td>142</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5.111117e+11</td>
      <td>136</td>
    </tr>
  </tbody>
</table>
</div>



# To identify the top 5 most purchased brands, based on the number of receipts scanned


```python
query = """
SELECT p.BRAND, 
       COUNT(t.RECEIPT_ID) AS total_purchases
FROM transactions t
JOIN products p ON t.BARCODE = p.BARCODE
GROUP BY p.BRAND
ORDER BY total_purchases DESC
LIMIT 5;
"""
pd.read_sql_query(query, conn)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>BRAND</th>
      <th>total_purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>COCA-COLA</td>
      <td>1080</td>
    </tr>
    <tr>
      <th>1</th>
      <td>None</td>
      <td>784</td>
    </tr>
    <tr>
      <th>2</th>
      <td>GREAT VALUE</td>
      <td>768</td>
    </tr>
    <tr>
      <th>3</th>
      <td>PEPSI</td>
      <td>732</td>
    </tr>
    <tr>
      <th>4</th>
      <td>EQUATE</td>
      <td>682</td>
    </tr>
  </tbody>
</table>
</div>



# To identify the top 5 highest-spending users based on their total spending on Fetch.




```python
query = """
SELECT t.USER_ID, 
       SUM(t.FINAL_SALE) AS total_spent,
       COUNT(t.RECEIPT_ID) AS total_receipts
FROM transactions t
GROUP BY t.USER_ID
ORDER BY total_spent DESC
LIMIT 5;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>USER_ID</th>
      <th>total_spent</th>
      <th>total_receipts</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>630789e1101ae272a4852287</td>
      <td>925.64</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>63af23db9f3fc9c7546fdbec</td>
      <td>476.34</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>650874eafe41d365c2ee11d2</td>
      <td>267.29</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>645add3bffe0d7e043ef1b63</td>
      <td>227.93</td>
      <td>8</td>
    </tr>
    <tr>
      <th>4</th>
      <td>637257e75fdbb03aa198a310</td>
      <td>194.14</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>



# To analyze monthly sales trends for 2024 by aggregating the total sales (FINAL_SALE) per month.


```python
query = """
SELECT strftime('%Y-%m', PURCHASE_DATE) AS month, 
       SUM(FINAL_SALE) AS total_sales
FROM transactions
WHERE strftime('%Y', PURCHASE_DATE) = '2024'
GROUP BY month
ORDER BY month;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>month</th>
      <th>total_sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2024-06</td>
      <td>36024.17</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2024-07</td>
      <td>64987.69</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2024-08</td>
      <td>58554.53</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2024-09</td>
      <td>12048.01</td>
    </tr>
  </tbody>
</table>
</div>



# To identifies the top 5 product categories by total sales based on transaction data.


```python
query = """
SELECT p.CATEGORY_1, 
       SUM(t.FINAL_SALE) AS total_sales
FROM transactions t
JOIN products p ON t.BARCODE = p.BARCODE
GROUP BY p.CATEGORY_1
ORDER BY total_sales DESC
LIMIT 5;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CATEGORY_1</th>
      <th>total_sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Snacks</td>
      <td>46717.75</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Health &amp; Wellness</td>
      <td>41447.74</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Beverages</td>
      <td>6537.06</td>
    </tr>
    <tr>
      <th>3</th>
      <td>None</td>
      <td>2371.34</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alcohol</td>
      <td>1223.49</td>
    </tr>
  </tbody>
</table>
</div>



# To identify which product categories have the highest number of missing BRAND values.




```python
query = """
SELECT p.CATEGORY_1, 
       COUNT(*) AS missing_brand_count
FROM products p
JOIN transactions t ON p.BARCODE = t.BARCODE
WHERE p.BRAND IS NULL OR p.BRAND = ''
GROUP BY p.CATEGORY_1
ORDER BY missing_brand_count DESC;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CATEGORY_1</th>
      <th>missing_brand_count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Snacks</td>
      <td>538</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Health &amp; Wellness</td>
      <td>246</td>
    </tr>
  </tbody>
</table>
</div>



# To analyze customer retention by identifying repeat buyers—users who make purchases across multiple months.


```python
query = """
WITH user_purchases AS (
    SELECT USER_ID, 
           strftime('%Y-%m', PURCHASE_DATE) AS purchase_month,
           SUM(FINAL_SALE) AS total_spent
    FROM transactions
    GROUP BY USER_ID, purchase_month
)
SELECT USER_ID, 
       COUNT(DISTINCT purchase_month) AS repeat_months,
       SUM(total_spent) AS total_spent,
       COUNT(*) AS total_purchases
FROM user_purchases
GROUP BY USER_ID
ORDER BY total_spent DESC
LIMIT 5;
"""
pd.read_sql_query(query, conn)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>USER_ID</th>
      <th>repeat_months</th>
      <th>total_spent</th>
      <th>total_purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>630789e1101ae272a4852287</td>
      <td>1</td>
      <td>925.64</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>63af23db9f3fc9c7546fdbec</td>
      <td>1</td>
      <td>476.34</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>650874eafe41d365c2ee11d2</td>
      <td>1</td>
      <td>267.29</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>645add3bffe0d7e043ef1b63</td>
      <td>3</td>
      <td>227.93</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>637257e75fdbb03aa198a310</td>
      <td>2</td>
      <td>194.14</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
