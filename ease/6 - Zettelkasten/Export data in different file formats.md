2026-06-19 16:57

Status:

Tags:

---


## 1) To CSV

```python
import pandas as pd

df = pd.read_csv("IPL Matches 2008-2020.csv")

# Here we groupby the city column and take the mean of the result_margin column
# We use .reset_index() to convert it back to a DataFrame from a Series object
temp = df.groupby("city")["result_margin"].mean().reset_index()
temp
````

||**city**|**result_margin**|
|---|---|---|
|**0**|Abu Dhabi|19.222222|
|**1**|Ahmedabad|19.818182|
|**30**|Sharjah|20.500000|
|**31**|Visakhapatnam|24.000000|



```Python
# index=False ensures that no extra index column stores/saves into the file
temp.to_csv('cityIPL.csv', index=False)

pd.read_csv('cityIPL.csv')
```

||**city**|**result_margin**|
|---|---|---|
|**0**|Abu Dhabi|19.222222|
|**1**|Ahmedabad|19.818182|
|**2**|Rajkot|13.111111|
|**3**|Ranchi|9.285714|

## 2) To Excel Sheet



```Python
df = pd.read_csv('cityIPL.csv')
df1 = df.head(10)
df2 = df.tail(10)

# Writing multiple dataframes to different sheets in a single file
with pd.ExcelWriter('output.xlsx') as writer:
    df1.to_excel(writer, sheet_name='batman_1', index=False)
    df2.to_excel(writer, sheet_name='batman_2', index=False)
```

## 3) To JSON



```Python
df = pd.read_csv("IPL Matches 2008-2020.csv")
df.head(2)
```

||**id**|**city**|**toss_winner**|**toss_decision**|**winner**|
|---|---|---|---|---|---|
|**0**|335982|Bangalore|Royal Challengers Bangalore|field|Kolkata Knight Riders|
|**1**|335983|Chandigarh|Chennai Super Kings|bat|Chennai Super Kings|



```Python
# Task: Create a table that shows the total sum of victory margins for every winning team, broken down by the city where the match took place.
# .unstack() converts Series data to a DataFrame grid format
df.groupby(['city', 'winner'])['result_margin'].sum().unstack().to_json('api.json')
```

## 4) To SQL



```Python
# Connection String & Connectivity Setup
# 1. Create the connection string
# format: dialect+driver://user:password@host:port/database
conn_str = "mysql+mysqlconnector://root:password@127.0.0.1:3306/world"

# 2. Create the engine
from sqlalchemy import create_engine
engine = create_engine(conn_str)

df = pd.read_csv("IPL Matches 2008-2020.csv")

# It adds the data to the running SQL Server (not into a local file)
# if_exists can be changed between 'replace' and 'append'
df.to_sql('ipl_winners', engine, if_exists='replace', index=False)
```



## References