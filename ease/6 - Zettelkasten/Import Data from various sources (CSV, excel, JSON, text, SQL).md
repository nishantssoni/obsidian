2026-06-19 16:18

Status:

Tags: [[sql]] [[json]] [[csv]]

---


# Working with CSV

```python
# Importing Pandas
import pandas as pd

df = pd.read_csv('aug_train.csv')
df
````

||**enrollee_id**|**city**|**city_development_index**|**gender**|**relevent_experience**|**enrolled_university**|**education_level**|
|---|---|---|---|---|---|---|---|
|**0**|8949|city_103|0.920|Male|Has relevent experience|no_enrollment|Graduate|
|**1**|29725|city_40|0.776|Male|No relevent experience|no_enrollment|Graduate|

## 3. Opening a CSV file from a URL


``` python
import requests
from io import StringIO

url = "https://raw.githubusercontent.com/cs109/2014_data/master/countries.csv"
headers = {"User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:66.0) Gecko/20100101 Firefox/66.0"}

req = requests.get(url, headers=headers)
data = StringIO(req.text)
pd.read_csv(data)
```

- **Note:** We have to pass headers to act like a client or browser.
    

||**Country**|**Region**|
|---|---|---|
|**0**|Algeria|AFRICA|
|**1**|Angola|AFRICA|
|**2**|Benin|AFRICA|

## 4. Sep Parameter


``` python
# index_col changes the default column index to the specific column we want
pd.read_csv('aug_train.csv', index_col='enrollee_id')
```

|**enrollee_id**|**city**|**city_development_index**|**gender**|
|---|---|---|---|
|**8949**|city_103|0.920|Male|
|...|...|...|...|
|**7386**|city_173|0.878|Male|

## 6. Header Parameter

``` python
pd.read_csv('test.csv')
```

- **Note:** The header is also considered the first row in this layout.
    

||**Unnamed: 0**|**Unnamed: 1**|**Unnamed: 2**|
|---|---|---|---|
|**0**|0|enrollee_id|city|
|**1**|1|29725|city_40|
|**2**|2|11561|city_21|
|**3**|3|33241|city_115|
|**4**|4|666|city_162|

Python

``` python
# We add header=1 which makes the first row the column name of the data
pd.read_csv('test.csv', header=1)
```

||**0**|**enrollee_id**|**city**|**city_development_index**|
|---|---|---|---|---|
|**0**|1|29725|city_40|0.776|
|**1**|2|11561|city_21|0.624|
|**2**|3|33241|city_115|0.789|
|**3**|4|666|city_162|0.767|

## 7. use_cols Parameter

Python

``` python
# We select only the specific parameters/columns which we want
pd.read_csv('aug_train.csv', usecols=['enrollee_id', 'gender', 'education_level'])
```

||**enrollee_id**|**gender**|**education_level**|
|---|---|---|---|
|**0**|8949|Male|Graduate|
|**4**|666|Male|Masters|
|...|...|...|...|
|**19153**|7386|Male|Graduate|

_19158 rows × 3 columns_

## 8. Squeeze Parameters


``` python
# This squeezes the dataframe to match the usecols column and converts it to Pandas Series data
pd.read_csv('aug_train.csv', usecols=['gender'], squeeze=True)
```


```
0    Male
1    Male
...
19157    NaN
Name: gender, Length: 19158, dtype: object
```

## Skiprows/nrows Parameter


``` python
# nrows restricts the number of rows.
# We use this when we have to deal with large data, so we take a part of it.
pd.read_csv('aug_train.csv', nrows=100)
```

||**enrollee_id**|**city**|**city_development_index**|**gender**|**relevent_experience**|**enrolled_university**|
|---|---|---|---|---|---|---|
|**0**|8949|city_103|0.920|Male|Has relevent experience|no_enrollment|
|**1**|29725|city_40|0.776|Male|No relevent experience|no_enrollment|
|...|...|...|...|...|...|...|
|**95**|12081|city_65|0.802|Male|Has relevent experience|Full time course|
|**96**|7364|city_160|0.920|NaN|No relevent experience|Full time course|
|**97**|11184|city_74|0.579|NaN|No relevent experience|Full time course|



---
---

## Advanced Pandas CSV and File Handling Operations

```python
pd.read_csv('zomato.csv')
````

- **Error Encountered:** `UnicodeDecodeError`
    
- **Fix:** Sometimes you get an encoding error. We add the correct encoding parameter to successfully read the data, or we can change the encoding in another text editor.



``` Python
pd.read_csv('zomato.csv', encoding='latin-1')
```

## 11. Skip bad lines


```Python
# We use this parameter when we encounter a Parse Error, allowing us to skip the bad line or row.
pd.read_csv('zomato.csv', encoding='latin-1', on_bad_lines='skip')
|   | Restaurant ID | Restaurant Name        | Country Code | City            |
|---|---------------|------------------------|--------------|-----------------|
| 0 | 6317637       | Le Petit Souffle       | 162          | Makati City     |
| 1 | 6304287       | Izakaya Kikufuji       | 162          | Makati City     |
| 2 | 6300002       | Heat - Edsa Shangri-La | 162          | Mandaluyong City|
| 3 | 6318506       | Ooma                   | 162          | Mandaluyong City|
```

The `on_bad_lines` parameter provides more explicit control over how "bad lines" (lines with too many or too few fields compared to the header) are handled. It accepts one of three string values: `'error'`, `'warn'`, or `'skip'`.

## 12. dtypes parameter



```Python
# We change the target column data type from float to int.
# .info() provides structural details about the columns.
pd.read_csv('aug_train.csv', dtype={'target': int}).info()
```



```Plaintext
# Column                Non-Null Count  Dtype
--- ------              --------------  -----
0   enrollee_id         19158 non-null  int64
1   city                19158 non-null  object
2   city_development_index 19158 non-null float64
...
12  training_hours      19158 non-null  int64
13  target              19158 non-null  int32
dtypes: float64(1), int32(1), int64(2), object(10)
```

- **Observation:** See, the data is successfully converted to the specified integer format.
    

## 13. Handling Dates



```Python
pd.read_csv('IPL Matches 2008-2020.csv', parse_dates=['date']).info()
```



```Plaintext
# Column          Non-Null Count  Dtype
--- ------        --------------  -----
0   id            816 non-null    int64
1   city          803 non-null    object
2   date          816 non-null    datetime64[ns]
3   player_of_match 812 non-null   object
14  method        19 non-null     object
15  umpire1       816 non-null    object
16  umpire2       816 non-null    object
```

- **Note:** By default, Pandas parses date columns as generic strings (`object`). We must explicitly use `parse_dates` to resolve it.
    
- **Observation:** Notice that it has successfully become a proper `datetime64[ns]` object.
    

## 14. Converters



```Python
# If we want to change or transform values across an entire column, 
# we can create a custom function and map it to the data.
def rename(name):
    if name == "Royal Challengers Bangalore":
        return "RCB"
    else:
        return name

rename("Royal Challengers Bangalore")
# Output: 'RCB'

pd.read_csv('IPL Matches 2008-2020.csv', converters={'team1': rename})
```

||**id**|**city**|**date**|**player_of_match**|**venue**|**neutral_venue**|**team1**|
|---|---|---|---|---|---|---|---|
|0|335982|Bangalore|2008-04-18|BB McCullum|M Chinnaswamy Stadium|0|RCB|
|1|335983|Chandigarh|2008-04-19|MEK Hussey|Punjab Cricket Association|0|Kings XI Punjab|
|4|335986|Kolkata|2008-04-20|DJ Hussey|Eden Gardens|0|Kolkata Knight Riders|
|...|...|...|...|...|...|...|...|
|811|1216547|Dubai|2020-09-28|AB de Villiers|Dubai International Stadium|0|RCB|

- **Observation:** See, the targets matching the filter criteria systematically change to 'RCB'.
    

## 15. na_values parameter



```Python
# Replaces specific unwanted values with NaN (Not a Number) missing value tokens.
# Here we pass 'Male', which replaces every occurrence of 'Male' in the dataset with NaN.
pd.read_csv('aug_train.csv', na_values=['Male'])
```

||**enrollee_id**|**city**|**city_development_index**|**gender**|**relevent_experience**|
|---|---|---|---|---|---|
|0|8949|city_103|0.920|NaN|Has relevent experience|
|1|29725|city_40|0.776|NaN|No relevent experience|
|2|11561|city_21|0.624|NaN|No relevent experience|
|...|...|...|...|...|...|
|19153|7386|city_173|0.878|NaN|No relevent experience|
|19157|23834|city_67|0.855|NaN|No relevent experience|

_19158 rows × 14 columns_

- **Strategy Note:** We can supply an entire list of custom strings to this parameter. We must always inspect our dataset for anomalous/unwanted values and explicitly map them to `NaN` when we don't want them skewing calculations.
    

## 16. Loading a huge dataset in chunks



```Python
# chunksize represents the row limit per iteration.
# It splits up massive datasets into manageable chunks to optimize runtime performance.
dfs = pd.read_csv('aug_train.csv', chunksize=5000)

for chunk in dfs:
    print(chunk.shape)
```

Plaintext

```
(4158, 14)
(4158, 14)
(4158, 14)
(4158, 14)
```

## Reading from Alternative Formats

### * Reading from an Excel file


```Python
# We can explicitly isolate a target worksheet by passing the sheet name parameter.
pd.read_excel('output.xlsx', sheet_name='sheet_3')
```

### * Reading from a Text (.txt) file


```Python
# We use the standard read_csv engine to process raw text files too.
# For example, text delimited or separated by tabs:
pd.read_csv("dog.txt", sep='\t')
```

### * Reading from a JSON dataset

- The implementation behaves the exact same way for JSON files.
    
- **Tip:** You can supply a direct URL link into the `read_json()` method to fetch and parse structural streaming API payloads directly.






# Fetching Data from SQL

```python
import pandas as pd
from sqlalchemy import create_engine

# # 1. Create the connection string
# # format: dialect+driver://user:password@host:port/database
# Note: You have to host the database in XAMPP, Docker, etc.
conn_str = "mysql+mysqlconnector://root:password@127.0.0.1:3306/world"

# # 2. Create the engine
engine = create_engine(conn_str)

# # 3. Read the data (No warning!)
df = pd.read_sql_query("SELECT * FROM city;", engine)
print(df.head())
````

Plaintext

```
   ID           Name CountryCode        District  Population
0   1          Kabul         AFG           Kabol     1780000
1   2       Qandahar         AFG        Qandahar      237500
2   3          Herat         AFG           Herat      186800
3   4 Mazar-e-Sharif         AFG           Balkh      127800
4   5      Amsterdam         NLD   Noord-Holland      731200
```

### Connection String Breakdown

Here is a one-line breakdown of that connection string format:

`dialect+driver://username:password@host:port/database`

#### Quick Reference Note:

- **mysql:** The database type (Dialect).
    
- **mysqlconnector:** The Python library used to talk to the DB (Driver).
    
- **root:** Your database administrative username.
    
- **password:** The password you set in your docker-compose.yml file.
    
- **127.0.0.1:** Your local computer's address (where Docker is running).
    
- **3306:** The specific "door" (Port) opened in your Compose file for MySQL.
    
- **world:** The specific database folder you want to open.






## References