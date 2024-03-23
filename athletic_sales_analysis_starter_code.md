```python
# Import Libraries and Dependencies
import pandas as pd
from pathlib import Path
```

### 1. Combine and Clean the Data
#### Import CSVs


```python
# Read the CSV files into DataFrames.
path_2020 = Path('Resources/athletic_sales_2020.csv')
path_2021 = Path('Resources/athletic_sales_2021.csv')

df_2020 = pd.read_csv(path_2020, index_col='retailer')
df_2021 = pd.read_csv(path_2021, index_col='retailer')
```


```python
# Display the 2020 sales DataFrame
df_2020
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
      <th>retailer_id</th>
      <th>invoice_date</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th>product</th>
      <th>price_per_unit</th>
      <th>units_sold</th>
      <th>total_sales</th>
      <th>operating_profit</th>
      <th>sales_method</th>
    </tr>
    <tr>
      <th>retailer</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>New York</td>
      <td>New York</td>
      <td>Men's Street Footwear</td>
      <td>50</td>
      <td>1200</td>
      <td>600000</td>
      <td>300000.00</td>
      <td>In-store</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Apparel</td>
      <td>68</td>
      <td>83</td>
      <td>5644</td>
      <td>2426.92</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Apparel</td>
      <td>75</td>
      <td>275</td>
      <td>206250</td>
      <td>61875.00</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>New York</td>
      <td>New York</td>
      <td>Men's Street Footwear</td>
      <td>34</td>
      <td>384</td>
      <td>13056</td>
      <td>6789.12</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Apparel</td>
      <td>53</td>
      <td>83</td>
      <td>4399</td>
      <td>1407.68</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>West Gear</th>
      <td>1128299</td>
      <td>12/30/20</td>
      <td>West</td>
      <td>California</td>
      <td>San Francisco</td>
      <td>Women's Apparel</td>
      <td>72</td>
      <td>203</td>
      <td>14616</td>
      <td>3946.32</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>West Gear</th>
      <td>1128299</td>
      <td>12/30/20</td>
      <td>West</td>
      <td>California</td>
      <td>San Francisco</td>
      <td>Women's Apparel</td>
      <td>80</td>
      <td>700</td>
      <td>560000</td>
      <td>84000.00</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <td>1189833</td>
      <td>12/30/20</td>
      <td>Midwest</td>
      <td>Minnesota</td>
      <td>Minneapolis</td>
      <td>Women's Street Footwear</td>
      <td>41</td>
      <td>119</td>
      <td>4879</td>
      <td>2878.61</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <td>1189833</td>
      <td>12/30/20</td>
      <td>Midwest</td>
      <td>Minnesota</td>
      <td>Minneapolis</td>
      <td>Women's Street Footwear</td>
      <td>45</td>
      <td>475</td>
      <td>213750</td>
      <td>96187.50</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>West Gear</th>
      <td>1128299</td>
      <td>12/30/20</td>
      <td>West</td>
      <td>California</td>
      <td>San Francisco</td>
      <td>Women's Apparel</td>
      <td>62</td>
      <td>245</td>
      <td>15190</td>
      <td>2886.10</td>
      <td>Outlet</td>
    </tr>
  </tbody>
</table>
<p>1297 rows × 11 columns</p>
</div>




```python
# Display the 2021 sales DataFrame
df_2021
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
      <th>retailer_id</th>
      <th>invoice_date</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th>product</th>
      <th>price_per_unit</th>
      <th>units_sold</th>
      <th>total_sales</th>
      <th>operating_profit</th>
      <th>sales_method</th>
    </tr>
    <tr>
      <th>retailer</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>West Gear</th>
      <td>1128299</td>
      <td>1/1/21</td>
      <td>West</td>
      <td>California</td>
      <td>San Francisco</td>
      <td>Men's Athletic Footwear</td>
      <td>65</td>
      <td>750</td>
      <td>487500</td>
      <td>121875.00</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>West Gear</th>
      <td>1128299</td>
      <td>1/1/21</td>
      <td>West</td>
      <td>California</td>
      <td>San Francisco</td>
      <td>Men's Athletic Footwear</td>
      <td>51</td>
      <td>233</td>
      <td>11883</td>
      <td>3208.41</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <td>1189833</td>
      <td>1/1/21</td>
      <td>Midwest</td>
      <td>Montana</td>
      <td>Billings</td>
      <td>Men's Apparel</td>
      <td>50</td>
      <td>275</td>
      <td>137500</td>
      <td>82500.00</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <td>1189833</td>
      <td>1/1/21</td>
      <td>Midwest</td>
      <td>Montana</td>
      <td>Billings</td>
      <td>Men's Apparel</td>
      <td>47</td>
      <td>77</td>
      <td>3619</td>
      <td>2714.25</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>West Gear</th>
      <td>1128299</td>
      <td>1/1/21</td>
      <td>West</td>
      <td>California</td>
      <td>San Francisco</td>
      <td>Men's Athletic Footwear</td>
      <td>64</td>
      <td>225</td>
      <td>14400</td>
      <td>5184.00</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Men's Apparel</td>
      <td>63</td>
      <td>47</td>
      <td>2961</td>
      <td>1362.06</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Men's Apparel</td>
      <td>46</td>
      <td>56</td>
      <td>2576</td>
      <td>1004.64</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>Amazon</th>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Maine</td>
      <td>Portland</td>
      <td>Men's Apparel</td>
      <td>52</td>
      <td>36</td>
      <td>1872</td>
      <td>692.64</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>Amazon</th>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Maine</td>
      <td>Portland</td>
      <td>Men's Apparel</td>
      <td>55</td>
      <td>125</td>
      <td>68750</td>
      <td>17187.50</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Men's Apparel</td>
      <td>70</td>
      <td>175</td>
      <td>122500</td>
      <td>42875.00</td>
      <td>Outlet</td>
    </tr>
  </tbody>
</table>
<p>8346 rows × 11 columns</p>
</div>



#### Check the data types of each DataFrame


```python
# Check the 2020 sales data types.
df_2020.dtypes
```




    retailer_id           int64
    invoice_date         object
    region               object
    state                object
    city                 object
    product              object
    price_per_unit        int64
    units_sold            int64
    total_sales           int64
    operating_profit    float64
    sales_method         object
    dtype: object




```python
# Check the 2021 sales data types.
df_2021.dtypes
```




    retailer_id           int64
    invoice_date         object
    region               object
    state                object
    city                 object
    product              object
    price_per_unit        int64
    units_sold            int64
    total_sales           int64
    operating_profit    float64
    sales_method         object
    dtype: object



#### Combine the sales data by rows.


```python
# Combine the 2020 and 2021 sales DataFrames on the rows and reset the index.
joined_data_rows_df= pd.concat([df_2020, df_2021], axis="rows", join="inner").reset_index()
joined_data_rows_df
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
      <th>retailer</th>
      <th>retailer_id</th>
      <th>invoice_date</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th>product</th>
      <th>price_per_unit</th>
      <th>units_sold</th>
      <th>total_sales</th>
      <th>operating_profit</th>
      <th>sales_method</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>New York</td>
      <td>New York</td>
      <td>Men's Street Footwear</td>
      <td>50</td>
      <td>1200</td>
      <td>600000</td>
      <td>300000.00</td>
      <td>In-store</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Apparel</td>
      <td>68</td>
      <td>83</td>
      <td>5644</td>
      <td>2426.92</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Apparel</td>
      <td>75</td>
      <td>275</td>
      <td>206250</td>
      <td>61875.00</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>New York</td>
      <td>New York</td>
      <td>Men's Street Footwear</td>
      <td>34</td>
      <td>384</td>
      <td>13056</td>
      <td>6789.12</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>1/1/20</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Apparel</td>
      <td>53</td>
      <td>83</td>
      <td>4399</td>
      <td>1407.68</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>9638</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Men's Apparel</td>
      <td>63</td>
      <td>47</td>
      <td>2961</td>
      <td>1362.06</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>9639</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Men's Apparel</td>
      <td>46</td>
      <td>56</td>
      <td>2576</td>
      <td>1004.64</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>9640</th>
      <td>Amazon</td>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Maine</td>
      <td>Portland</td>
      <td>Men's Apparel</td>
      <td>52</td>
      <td>36</td>
      <td>1872</td>
      <td>692.64</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>9641</th>
      <td>Amazon</td>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Maine</td>
      <td>Portland</td>
      <td>Men's Apparel</td>
      <td>55</td>
      <td>125</td>
      <td>68750</td>
      <td>17187.50</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>9642</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>12/31/21</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Men's Apparel</td>
      <td>70</td>
      <td>175</td>
      <td>122500</td>
      <td>42875.00</td>
      <td>Outlet</td>
    </tr>
  </tbody>
</table>
<p>9643 rows × 12 columns</p>
</div>




```python
# Check if any values are null.
joined_data_rows_df.isnull().any()
```




    retailer            False
    retailer_id         False
    invoice_date        False
    region              False
    state               False
    city                False
    product             False
    price_per_unit      False
    units_sold          False
    total_sales         False
    operating_profit    False
    sales_method        False
    dtype: bool




```python
# Check the data type of each column
joined_data_rows_df.dtypes
```




    retailer             object
    retailer_id           int64
    invoice_date         object
    region               object
    state                object
    city                 object
    product              object
    price_per_unit        int64
    units_sold            int64
    total_sales           int64
    operating_profit    float64
    sales_method         object
    dtype: object




```python
# Convert the "invoice_date" to a datetime datatype
joined_data_rows_df['invoice_date'] = pd.to_datetime(joined_data_rows_df['invoice_date'],format='mixed')
```


```python
# Confirm that the "invoice_date" data type has been changed.
joined_data_rows_df.dtypes
```




    retailer                    object
    retailer_id                  int64
    invoice_date        datetime64[ns]
    region                      object
    state                       object
    city                        object
    product                     object
    price_per_unit               int64
    units_sold                   int64
    total_sales                  int64
    operating_profit           float64
    sales_method                object
    dtype: object



### 2. Determine which Region Sold the Most Products

#### Using `groupby`


```python
# Show the number products sold for region, state, and city.
# Rename the sum to "Total_Products_Sold".

df_total_products_sold_agg = joined_data_rows_df.groupby(['region','state','city'],as_index=True)['units_sold'].agg(['sum'])
df_total_products_sold_agg = df_total_products_sold_agg.rename(columns={'sum':'Total_Poducts_Sold'})


# Show the top 5 results.
df_total_products_sold_agg= df_total_products_sold_agg.sort_values(by='Total_Poducts_Sold', ascending=False)
df_total_products_sold_agg.head()
                            
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
      <th></th>
      <th></th>
      <th>Total_Poducts_Sold</th>
    </tr>
    <tr>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>111954</td>
    </tr>
    <tr>
      <th>South</th>
      <th>Texas</th>
      <th>Houston</th>
      <td>90322</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">West</th>
      <th rowspan="2" valign="top">California</th>
      <th>San Francisco</th>
      <td>85478</td>
    </tr>
    <tr>
      <th>Los Angeles</th>
      <td>76384</td>
    </tr>
    <tr>
      <th>Southeast</th>
      <th>Florida</th>
      <th>Miami</th>
      <td>73135</td>
    </tr>
  </tbody>
</table>
</div>



#### Using `pivot_table`


```python
# Show the number products sold for region, state, and city.
df_total_products_sold_pivot = joined_data_rows_df.pivot_table(index = ['region','state','city'],values='units_sold',aggfunc='sum')

# Rename the "units_sold" column to "Total_Products_Sold"
df_total_products_sold_pivot = df_total_products_sold_pivot.rename(columns={'units_sold':'Total_Poducts_Sold'})

# Show the top 5 results.
df_total_products_sold_pivot= df_total_products_sold_pivot.sort_values(by='Total_Poducts_Sold', ascending=False)
df_total_products_sold_pivot.head()
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
      <th></th>
      <th></th>
      <th>Total_Poducts_Sold</th>
    </tr>
    <tr>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>111954</td>
    </tr>
    <tr>
      <th>South</th>
      <th>Texas</th>
      <th>Houston</th>
      <td>90322</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">West</th>
      <th rowspan="2" valign="top">California</th>
      <th>San Francisco</th>
      <td>85478</td>
    </tr>
    <tr>
      <th>Los Angeles</th>
      <td>76384</td>
    </tr>
    <tr>
      <th>Southeast</th>
      <th>Florida</th>
      <th>Miami</th>
      <td>73135</td>
    </tr>
  </tbody>
</table>
</div>



### 3. Determine which Region had the Most Sales

#### Using `groupby`


```python
# Show the total sales for the products sold for each region, state, and city.
# Rename the "total_sales" column to "Total Sales"
df_total_sales_agg = joined_data_rows_df.groupby(['region','state','city'])['total_sales'].agg(['sum'])

df_total_sales_agg = df_total_sales_agg.rename(columns={'sum':'Total_Sales'})

# Show the top 5 results.
df_total_sales_agg= df_total_sales_agg.sort_values(by='Total_Sales', ascending=False)
df_total_sales_agg.head()
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
      <th></th>
      <th></th>
      <th>Total_Sales</th>
    </tr>
    <tr>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>39801235</td>
    </tr>
    <tr>
      <th>West</th>
      <th>California</th>
      <th>San Francisco</th>
      <td>33973228</td>
    </tr>
    <tr>
      <th rowspan="3" valign="top">Southeast</th>
      <th>Florida</th>
      <th>Miami</th>
      <td>31600863</td>
    </tr>
    <tr>
      <th>South Carolina</th>
      <th>Charleston</th>
      <td>29285637</td>
    </tr>
    <tr>
      <th>Florida</th>
      <th>Orlando</th>
      <td>27682851</td>
    </tr>
  </tbody>
</table>
</div>



#### Using `pivot_table`


```python
# Show the total sales for the products sold for each region, state, and city.
df_total_sales_pivot = joined_data_rows_df.pivot_table(index = ['region','state','city'],values='total_sales',aggfunc='sum')

# Optional: Rename the "total_sales" column to "Total Sales"
df_total_sales_pivot = df_total_sales_pivot.rename(columns={'total_sales':'Total_Sales'})

# Show the top 5 results.
df_total_sales_pivot= df_total_sales_pivot.sort_values(by='Total_Sales', ascending=False)
df_total_sales_pivot.head()
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
      <th></th>
      <th></th>
      <th>Total_Sales</th>
    </tr>
    <tr>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>39801235</td>
    </tr>
    <tr>
      <th>West</th>
      <th>California</th>
      <th>San Francisco</th>
      <td>33973228</td>
    </tr>
    <tr>
      <th rowspan="3" valign="top">Southeast</th>
      <th>Florida</th>
      <th>Miami</th>
      <td>31600863</td>
    </tr>
    <tr>
      <th>South Carolina</th>
      <th>Charleston</th>
      <td>29285637</td>
    </tr>
    <tr>
      <th>Florida</th>
      <th>Orlando</th>
      <td>27682851</td>
    </tr>
  </tbody>
</table>
</div>



### 4. Determine which Retailer had the Most Sales

#### Using `groupby`


```python
# Show the total sales for the products sold for each retailer, region, state, and city.
# Rename the "total_sales" column to "Total Sales"
df_total_sales_agg = joined_data_rows_df.groupby(['retailer','region','state','city'])['total_sales'].agg(['sum'])
df_total_sales_agg = df_total_sales_agg.rename(columns={'sum':'Total_Sales'})
# Show the top 5 results.
df_total_sales_agg= df_total_sales_agg.sort_values(by='Total_Sales', ascending=False)
df_total_sales_agg.head()
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
      <th></th>
      <th></th>
      <th></th>
      <th>Total_Sales</th>
    </tr>
    <tr>
      <th>retailer</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>West Gear</th>
      <th>West</th>
      <th>California</th>
      <th>San Francisco</th>
      <td>32794405</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <th>West</th>
      <th>California</th>
      <th>Los Angeles</th>
      <td>25127160</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>25008568</td>
    </tr>
    <tr>
      <th>West Gear</th>
      <th>West</th>
      <th>Washington</th>
      <th>Seattle</th>
      <td>24862675</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Southeast</th>
      <th>South Carolina</th>
      <th>Charleston</th>
      <td>24822280</td>
    </tr>
  </tbody>
</table>
</div>



#### Using `pivot_table`


```python
# Show the total sales for the products sold for each retailer, region, state, and city.
df_total_sales_pivot = joined_data_rows_df.pivot_table(index = ['retailer','region','state','city'],values='total_sales',aggfunc='sum')

# Optional: Rename the "total_sales" column to "Total Sales"
df_total_sales_pivot = df_total_sales_pivot.rename(columns={'total_sales':'Total_Sales'})

# Show the top 5 results.
df_total_sales_pivot= df_total_sales_pivot.sort_values(by='Total_Sales', ascending=False)
df_total_sales_pivot.head()

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
      <th></th>
      <th></th>
      <th></th>
      <th>Total_Sales</th>
    </tr>
    <tr>
      <th>retailer</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>West Gear</th>
      <th>West</th>
      <th>California</th>
      <th>San Francisco</th>
      <td>32794405</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <th>West</th>
      <th>California</th>
      <th>Los Angeles</th>
      <td>25127160</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>25008568</td>
    </tr>
    <tr>
      <th>West Gear</th>
      <th>West</th>
      <th>Washington</th>
      <th>Seattle</th>
      <td>24862675</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Southeast</th>
      <th>South Carolina</th>
      <th>Charleston</th>
      <td>24822280</td>
    </tr>
  </tbody>
</table>
</div>



### 5. Determine which Retailer Sold the Most Women's Athletic Footwear


```python
# Filter the sales data to get the women's athletic footwear sales data.
df_wfa_footware = joined_data_rows_df[joined_data_rows_df['product'].str.contains("Women's Athletic Footwear")]
df_wfa_footware.head()
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
      <th>retailer</th>
      <th>retailer_id</th>
      <th>invoice_date</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th>product</th>
      <th>price_per_unit</th>
      <th>units_sold</th>
      <th>total_sales</th>
      <th>operating_profit</th>
      <th>sales_method</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>21</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>2020-01-04</td>
      <td>Northeast</td>
      <td>New York</td>
      <td>New York</td>
      <td>Women's Athletic Footwear</td>
      <td>36</td>
      <td>281</td>
      <td>10116</td>
      <td>3742.92</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>2020-01-04</td>
      <td>Northeast</td>
      <td>New York</td>
      <td>New York</td>
      <td>Women's Athletic Footwear</td>
      <td>41</td>
      <td>247</td>
      <td>10127</td>
      <td>4658.42</td>
      <td>Online</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Foot Locker</td>
      <td>1185732</td>
      <td>2020-01-04</td>
      <td>Northeast</td>
      <td>New York</td>
      <td>New York</td>
      <td>Women's Athletic Footwear</td>
      <td>45</td>
      <td>850</td>
      <td>382500</td>
      <td>133875.00</td>
      <td>In-store</td>
    </tr>
    <tr>
      <th>26</th>
      <td>West Gear</td>
      <td>1128299</td>
      <td>2020-01-05</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Athletic Footwear</td>
      <td>45</td>
      <td>300</td>
      <td>135000</td>
      <td>47250.00</td>
      <td>Outlet</td>
    </tr>
    <tr>
      <th>27</th>
      <td>West Gear</td>
      <td>1128299</td>
      <td>2020-01-05</td>
      <td>Northeast</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>Women's Athletic Footwear</td>
      <td>34</td>
      <td>90</td>
      <td>3060</td>
      <td>1254.60</td>
      <td>Outlet</td>
    </tr>
  </tbody>
</table>
</div>



#### Using `groupby`


```python
# Show the total number of women's athletic footwear sold for each retailer, region, state, and city.
# Rename the "units_sold" column to "Womens_Footwear_Units_Sold"
df_wfa_sold_agg = df_wfa_footware.groupby(['retailer','region','state','city'])['units_sold'].agg(['sum'])
df_wfa_sold_agg = df_wfa_sold_agg.rename(columns={'sum':'Womens_Footwear_Units_Sold_Sales'})
# Show the top 5 results.
df_wfa_sold_agg= df_wfa_sold_agg.sort_values(by='Womens_Footwear_Units_Sold_Sales', ascending=False)
df_wfa_sold_agg.head()
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
      <th></th>
      <th></th>
      <th></th>
      <th>Womens_Footwear_Units_Sold_Sales</th>
    </tr>
    <tr>
      <th>retailer</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>West Gear</th>
      <th>West</th>
      <th>California</th>
      <th>San Francisco</th>
      <td>12107</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>10996</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <th>West</th>
      <th>California</th>
      <th>Los Angeles</th>
      <td>10826</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Southeast</th>
      <th>South Carolina</th>
      <th>Charleston</th>
      <td>8814</td>
    </tr>
    <tr>
      <th>Sports Direct</th>
      <th>South</th>
      <th>Texas</th>
      <th>Dallas</th>
      <td>8790</td>
    </tr>
  </tbody>
</table>
</div>



#### Using `pivot_table`


```python
# Show the total number of women's athletic footwear sold for each retailer, region, state, and city.
df_wfa_sold_pivot = df_wfa_footware.pivot_table(index = ['retailer','region','state','city'],values='units_sold',aggfunc='sum')

# Rename the "units_sold" column to "Womens_Footwear_Units_Sold"
df_wfa_sold_pivot = df_wfa_sold_pivot.rename(columns={'units_sold':'Womens_Footwear_Units_Sold'})
# Show the top 5 results.
df_wfa_sold_pivot= df_wfa_sold_pivot.sort_values(by='Womens_Footwear_Units_Sold', ascending=False)
df_wfa_sold_pivot.head()
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
      <th></th>
      <th></th>
      <th></th>
      <th>Womens_Footwear_Units_Sold</th>
    </tr>
    <tr>
      <th>retailer</th>
      <th>region</th>
      <th>state</th>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>West Gear</th>
      <th>West</th>
      <th>California</th>
      <th>San Francisco</th>
      <td>12107</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Northeast</th>
      <th>New York</th>
      <th>New York</th>
      <td>10996</td>
    </tr>
    <tr>
      <th>Kohl's</th>
      <th>West</th>
      <th>California</th>
      <th>Los Angeles</th>
      <td>10826</td>
    </tr>
    <tr>
      <th>Foot Locker</th>
      <th>Southeast</th>
      <th>South Carolina</th>
      <th>Charleston</th>
      <td>8814</td>
    </tr>
    <tr>
      <th>Sports Direct</th>
      <th>South</th>
      <th>Texas</th>
      <th>Dallas</th>
      <td>8790</td>
    </tr>
  </tbody>
</table>
</div>



### 5. Determine the Day with the Most Women's Athletic Footwear Sales


```python
# Create a pivot table with the 'invoice_date' column is the index, and the "total_sales" as the values.
df_invoice_date_sales_pivot = df_wfa_footware.pivot_table(index = ['invoice_date'],values='total_sales',aggfunc='sum')

# Optional: Rename the "total_sales" column to "Total Sales"
df_invoice_date_sales_pivot = df_invoice_date_sales_pivot.rename(columns={'total_sales':'Total Sales'})

# Show the table.
df_invoice_date_sales_pivot
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
      <th>Total Sales</th>
    </tr>
    <tr>
      <th>invoice_date</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-04</th>
      <td>402743</td>
    </tr>
    <tr>
      <th>2020-01-05</th>
      <td>141801</td>
    </tr>
    <tr>
      <th>2020-01-11</th>
      <td>129556</td>
    </tr>
    <tr>
      <th>2020-01-17</th>
      <td>173013</td>
    </tr>
    <tr>
      <th>2020-01-22</th>
      <td>388250</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>2021-12-22</th>
      <td>200406</td>
    </tr>
    <tr>
      <th>2021-12-23</th>
      <td>808022</td>
    </tr>
    <tr>
      <th>2021-12-24</th>
      <td>190885</td>
    </tr>
    <tr>
      <th>2021-12-25</th>
      <td>315175</td>
    </tr>
    <tr>
      <th>2021-12-30</th>
      <td>167903</td>
    </tr>
  </tbody>
</table>
<p>355 rows × 1 columns</p>
</div>




```python
# Resample the pivot table into daily bins, and get the total sales for each day.
df= df_invoice_date_sales_pivot.resample('D').sum()

# Sort the resampled pivot table in ascending order on "Total Sales".
df1 =df.sort_values(by='Total Sales', ascending=False)
df1.head(10)
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
      <th>Total Sales</th>
    </tr>
    <tr>
      <th>invoice_date</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-07-16</th>
      <td>1521825</td>
    </tr>
    <tr>
      <th>2021-12-16</th>
      <td>1473497</td>
    </tr>
    <tr>
      <th>2021-06-17</th>
      <td>1376988</td>
    </tr>
    <tr>
      <th>2021-08-17</th>
      <td>1086294</td>
    </tr>
    <tr>
      <th>2021-07-23</th>
      <td>1021806</td>
    </tr>
    <tr>
      <th>2021-11-17</th>
      <td>1021145</td>
    </tr>
    <tr>
      <th>2021-12-09</th>
      <td>915011</td>
    </tr>
    <tr>
      <th>2021-06-24</th>
      <td>884238</td>
    </tr>
    <tr>
      <th>2021-07-09</th>
      <td>869054</td>
    </tr>
    <tr>
      <th>2021-08-10</th>
      <td>839120</td>
    </tr>
  </tbody>
</table>
</div>



### 6.  Determine the Week with the Most Women's Athletic Footwear Sales


```python
# Resample the pivot table into weekly bins, and get the total sales for each week.
weekly_bins_total_sales_df = df_invoice_date_sales_pivot.resample('W').sum()

# Sort the resampled pivot table in ascending order on "Total Sales".
weekly_bins_total_sales_df= weekly_bins_total_sales_df.sort_values(by='Total Sales', ascending=False)
weekly_bins_total_sales_df.head(10)

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
      <th>Total Sales</th>
    </tr>
    <tr>
      <th>invoice_date</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-12-19</th>
      <td>3098970</td>
    </tr>
    <tr>
      <th>2021-12-12</th>
      <td>2922161</td>
    </tr>
    <tr>
      <th>2021-07-11</th>
      <td>2835078</td>
    </tr>
    <tr>
      <th>2021-07-18</th>
      <td>2801449</td>
    </tr>
    <tr>
      <th>2021-11-14</th>
      <td>2531721</td>
    </tr>
    <tr>
      <th>2021-08-22</th>
      <td>2491259</td>
    </tr>
    <tr>
      <th>2021-08-15</th>
      <td>2463941</td>
    </tr>
    <tr>
      <th>2021-11-21</th>
      <td>2449537</td>
    </tr>
    <tr>
      <th>2021-05-16</th>
      <td>2422132</td>
    </tr>
    <tr>
      <th>2021-06-13</th>
      <td>2358602</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
